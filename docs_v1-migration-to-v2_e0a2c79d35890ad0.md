> Source: https://docs.ns-api.com/docs/v1-migration-to-v2

This guide covers the main differences when starting to use V2 (ns-api/v2) for those developers familiar with the v1 (/ns-api) api.

* The API no longer supports XML format; JSON is now the only supported format.
* List/read requests will be returned in array format even if there's only one result. Specific resource requests will be returned as objects.
* A 404 error will be returned for read, update, or delete requests if the requested resource is unavailable.
* Error responses will now be in valid JSON format, containing "code" and "message" fields, providing more detailed data instead of within headers.
* Success messages will consistently use JSON; for HTTP status 202, a "code" and "message" will be provided if applicable.
* Some POST APIs introduce a "synchronous" option, returning a 200 response instead of 202, along with a complete JSON representation of the created data. More info [here](/docs/async-202-vs-sync-200).
* The tilde character "~" can be used to represent "my" in various contexts. For instance, using it for {domain} or {user} in the path will automatically substitute it with valid data from the authentication token/key.

* When creating a domain using the V2 API, the "domain" user will also be created. All options for the domain user can be provided during domain creation and will be saved for the default user.
* By default, the V2 API creates a dial plan with the same name as the domain and establishes a dial rule to link to system defaults.
* Field names have been updated and mapped to more descriptive names.
* Added ability to toggle recording on/off in the domain create/update
* Removed deprecated fields "rating" and "dial\_match".

* The V2 API now creates a default answer rule upon user creation and performs sim ringing across all devices.
* Handling of "dir" (now "directory-name-number-dtmf-mapping") is automated; manual setting is unnecessary.
* The term "subscriber" used in V1 has been deprecated in favor of "user."
* Field names have been changed and mapped to more descriptive names.
* New "site" is created if "site" given and that site doesn't exist previously.
* Added ability to toggle recording on/off in the User create/update

* Field names have been updated and mapped to more descriptive names.
* Merged Timeframe's and Timerange's to allow for a single request with time ranges inlcuded in a multi level JSON request under time-range-data field.
* Better handling of default fields so not all options are needed.

* The answer rule system has been completely redesigned. For more details, refer to [this link](/reference/post_domains-domain-users-user-answerrules).
* Each feature now corresponds to an object with "enable" and "parameters" fields, incorporating time-frame information within the key.

* The call\_processing\_rules have been split into distinct fields, enhancing control.
* If not provided, the default SIP password will now consist of 16 characters.
* Previously concealed fields such as registration time, accept agent, and latency reporting values are now included.
* Added ability to toggle recording on/off in the device create/update
* Field names have been updated and mapped to more descriptive names.

* Field names have been updated and mapped to more descriptive names.
* The "reseller\_id" and "entry\_status" parameters have been deprecated/removed as they were unused.
* Improved validation during creation and deletion, rejecting operations if domains already exist.

* Field names have been updated and mapped to more descriptive names.
* Added ability to toggle recording on/off in the callqueue create/update
* Enumeration values for "huntgroup\_option" (now "callqueue-dispatch-type") have been adjusted for improved representation and alignment with portal terminology. For more details, see [this link](/reference/post_domains-domain-callqueues).

* Field names have been updated and mapped to more descriptive names.
* New Action APIs consolidate three API calls into one. Previously, separate calls were needed for agent update, agent log creation, and subscriber update to handle login or logout. These actions are now streamlined using the new paths: /login, /logout, or /{status}. For more details, refer to [this link](/reference/agentlogin).
* Enumeration values for "entry\_option" (now "callqueue-agent-availability-type") have been revised to better represent their meanings and align with Portal terminology.
* Enumeration values for "entry\_device" (now "callqueue-agent-has-registered-devices") have been updated for clearer representation. For more details, see [this link](/reference/post_domains-domain-callqueues).

* Field names have been updated and mapped to more descriptive names.
* Phone numbers have been separated from the Dial rule object, with the new field "phonenumber" serving as the key. Fields such as "source" ,"valid range", "time of day" have been deprecated. If you need them then using Dialrule path would allow this from SU level.
* Enhanced duplicate protection has been implemented.
* Database structure has been optimized for faster lookup (DB read) speeds.
* Responder values have been aligned with new values. More info [here](/docs/application-mapping-in-phonenumbers-dialrules).

* Media and audio elements have transitioned from objects with filename keys to an array of objects.
* Field names have been updated and mapped to more descriptive names.
* URL encoding has been improved to handle '&' characters more effectively.
* Built in support for TTS for MOH, Mesg and Greetings. Will parse UI configs for language defaults or access params.
* Move to support new audio via 3 formats. TTS, Base64 encoded in JSON and form based File Upload to maximize supportability in different languages.