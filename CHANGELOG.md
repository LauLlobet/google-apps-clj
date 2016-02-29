# google-apps-clj changes


0.4.2 (2016-02-29)
------------------

**Features**

* Allow specifying default credential location using a System Property called `GOOGLE_APPLICATION_CREDENTIALS`
(this previously could be done with an environment variable of the same name; the system property will take precedence,
and if neither a system property nor an environment variable is specified, we'll still fall back to the Google
client library's default behavior, which also searches a predetermined file location)

**Documentation**

* Added documentation in [doc/RELEASING.md](doc/RELEASING.md) covering steps needed to cut a new release of this library


0.4.1 (2016-02-26)
------------------

**Bug Fixes**

* Fixed two slight dependency mismatches between `com.google.gdata/core` and other
Google dependencies, by adding exclusions to `com.google.gdata/core`:
  - `com.google.code.findbugs/jsr305` is `1.3.7` in `gdata/core`, `1.3.9` elsewhere
  - `org.apache.httpcomponents/httpclient` is `4.0.1` in `gdata/core`, `4.0.3` elsewhere


0.4.0 (2016-02-25)
------------------

**Breaking Changes**

* Many functions which previously were annotated to take a `credentials/GoogleCtx` map,
can now also accept a `GoogleCredential`. This changes the annotation to `credentials/GoogleAuth`.

**Features**

* Add support for [Service Account credentials](https://developers.google.com/identity/protocols/OAuth2ServiceAccount)
* Add helper methods for loading credentials, including [application default credentials](https://developers.google.com/identity/protocols/application-default-credentials)
* Add option to `google-drive/upload!` to prevent automatic conversion to Google Docs
* Improvements to `core.typed` annotations (still not complete)

**Documentation**

* Better changelog format
* Improved documentation to match new Google Developer Console
* Added instructions on how to obtain and use Service Account Credentials


0.3.3 (2016-01-14)
----------------------------------------

**Bug Fixes**

* Fix GoogleCtx type


0.3.2 (2016-01-13)
----------------------------------------

**Breaking Changes**

* Rename resolve-file-id! to find-file!, change semantics


0.3.1 (2016-01-08)
----------------------------------------

**Bug Fixes**

* Downgrade core.typed to 0.3.14


0.3.0 (2016-01-08)
----------------------------------------

**Features**

* Began tracking changes

**Breaking Changes**

* Major breaking changes to the drive ns, reworking it around
  queries as data structures. This allows them to be modified
  independently of their execution context (e.g. specifying fields)
  and also faciliates the single and batched execution contexts.




--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------

### :warning: **WARNING** :warning:

**Changelog from 0.2.2 and earlier is reconstructed and may not be 100% accurate!**

--------------------------------------------------------------------------------
--------------------------------------------------------------------------------


0.2.2 (2015-11-16)
----------------------------------------

**Features**

* In `google-drive`: Add `get-file-ids` to enumerate id:title map of all files
* In `google-drive`: Add `get-file` to fetch a File based on its ID


0.2.1 (2015-06-25)
----------------------------------------

**Bug Fixes**

* In `google-sheets`: `write-worksheet` resizes directly to the size we need
in order to avoid breaking frozen rows/columns


0.2.0 (2015-06-23)
----------------------------------------

**Features**

* New namespace `google-calendar`


0.1.3 (2015-06-22)
----------------------------------------

**Features**

* Many additions to `google-drive`


0.1.2 (2015-06-19)
----------------------------------------

**Misc**

* Transferred repo into SparkFund org
* Updated license from EPL to Apache 2.0


0.1.1 (2015-06-16)
----------------------------------------

**Features**

* Initial release