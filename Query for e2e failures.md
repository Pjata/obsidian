```splunk
index="jenkins_statistics" job_name="Catalog/catalog-e2e-nightly-run" trigger_by="Started by timer" | dedup build_url
                | fields job_result, job_name
                | eval success=if(job_result=="SUCCESS", 1, 0)
                | eval failure=if(job_result=="FAILURE", 1, 0)
                | eval aborted=if(job_result=="ABORTED", 1, 0)
                | search success=1 OR failure =1
                | table success, failure, _time
                | sort by _time
                ```