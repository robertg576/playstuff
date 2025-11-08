> Source: https://docs.ns-api.com/reference/put_domains-domain-users-user-timeframes-id

# Replace All Date Ranges in Specific Dates Timeframe

put https://{server}/ns-api/v2/domains//users//timeframes/

If a new array of specific date ranges is supplied in the update request for a Specific Dates timeframe, it will replace all existing specific date ranges in the timeframe, meaning that any existing specific date ranges in that timeframe will be removed. To update individual specific date ranges within a Specific Dates timeframe, refer to "Update Date Ranges within Specific Dates Timeframe." It is not necessary to supply a `timeframe-id` for the new date ranges. These `timeframe-id`s will be generated automatically.