```
 | dedup build_url
                | fields job_result
                | eval success=if(job_result=="SUCCESS", 1, 0)
                | eval failure=if(job_result=="FAILURE", 1, 0)
                | eval aborted=if(job_result=="ABORTED", 1, 0)
                | timechart span=1d sum(success) as success, sum(failure) as failure, sum(aborted) as aborted, count
                | eval success%=success/count * 100
                | eval failure%=failure/count * 100
                | eval aborted%=aborted/count * 100
                | timechart span=1d avg(success%) as success, avg(failure%) as failure, avg(aborted%) as aborted
