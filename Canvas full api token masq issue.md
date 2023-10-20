``` def has_subset_of_account_permissions?(user, account)
    return true if user == self
    return false unless account.root_account?

    Rails.cache.fetch(["has_subset_of_account_permissions", self, user, account].cache_key, expires_in: 60.minutes) do
      account_users = account.cached_all_account_users_for(self)
      account_users.all? do |account_user|
        account_user.is_subset_of?(user)
      end
    end
  end
