FROM registry.rocket.chat/rocketchat/rocket.chat:latest

ENV PORT='3000'
ENV MONGO_URL=mongodb://chat_db:27017/rocketchat
ENV MONGO_OPLOG_URL=mongodb://chat_db:27017/local

ENV OVERWRITE_SETTING_LDAP_User_Search_Field=cn
ENV OVERWRITE_SETTING_LDAP_Sync_User_Avatar=false
ENV OVERWRITE_SETTING_Accounts_TwoFactorAuthentication_By_TOTP_Enabled=false
ENV OVERWRITE_SETTING_Accounts_TwoFactorAuthentication_By_Email_Enabled=false
ENV OVERWRITE_SETTING_Accounts_TwoFactorAuthentication_Enforce_Password_Fallback=false
ENV OVERWRITE_SETTING_Accounts_TwoFactorAuthentication_Enabled=false
ENV OVERWRITE_SETTING_UI_Use_Real_Name=true

ENV OVERWRITE_SETTING_LDAP_Username_Field=cn

ENV OVERWRITE_SETTING_LDAP_LDAP_Login_Fallback=true
ENV OVERWRITE_SETTING_LDAP_Enable=true

ENV OVERWRITE_SETTING_LDAP_Authentication=true
ENV OVERWRITE_SETTING_LDAP_Authentication_UserDN=cn=admin,dc=example,dc=org
ENV OVERWRITE_SETTING_LDAP_Authentication_Password=secret


ENV OVERWRITE_SETTING_LDAP_BaseDN=dc=example,dc=org
ENV OVERWRITE_SETTING_LDAP_Host=ldap
ENV OVERWRITE_SETTING_LDAP_AD_User_Search_Field=uid


ENV OVERWRITE_SETTING_Allow_Marketing_Emails=false
ENV OVERWRITE_SETTING_Apps_Framework_enabled=false
ENV OVERWRITE_SETTING_Statistics_reporting=false
ENV OVERWRITE_SETTING_Show_Setup_Wizard=completed

CMD ["bash", "-c", "\
        for i in `seq 1 30`; do \
          node main.js && \
          s=$$? && break || s=$$?; \
          echo \"Tried $$i times. Waiting 5 secs...\"; \
          sleep 5; \
        done; (exit $$s)"] 