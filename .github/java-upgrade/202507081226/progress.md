# Upgrade Progress
### ✅ Generate plan    [View Log](logs\1-generatePlan.log)


### ✅ Confirm Plan    [View Log](logs\2-confirmPlan.log)


### ✅ Precheck - Build project    [View Log](logs\3-precheck-build.log)


### ✅ Precheck - Run tests    [View Log](logs\4-precheck-runTests.log)

<details>
    <summary>[ click to toggle details ]</summary>

#### Test result
| Total | Passed | Failed | Skipped | Errors |
        |-------|--------|--------|---------|--------|
        | 56 | 54 | 0 | 2 | 0 |



</details>


### ✅ Upgrade project using OpenRewrite    [View Log](logs\5-openrewrite.log)
3 files changed, 8 insertions(+), 7 deletions(-)
<details>
    <summary>[ click to toggle details ]</summary>

#### Recipes
- [org.openrewrite.java.migrate.UpgradeToJava21](https://docs.openrewrite.org/recipes/java/migrate/UpgradeToJava21)



</details>


### ✅ Build project    [View Log](logs\6-buildProject.log)


### ✅ Summarize code changes    [View Log](logs\7-summarizeFixes.log)

<details>
    <summary>[ click to toggle details ]</summary>

#### Code Changes
- Apply OpenRewrite Java 21 upgrade recipes
  - Upgrade language level to Java 21
  - Apply automated code modernization patterns



</details>


### ✅ Validate code behavior changes    [View Log](logs\8-validateBehaviorChanges.log)


### ✅ Run tests    [View Log](logs\9-runTests.log)

<details>
    <summary>[ click to toggle details ]</summary>

#### Test result
| Total | Passed | Failed | Skipped | Errors |
|-------|--------|--------|---------|--------|
| 56 | 54 | 0 | 2 | 0 |



</details>


### ✅ Validate CVEs    [View Log](logs\10-validateCves.log)

<details>
    <summary>[ click to toggle details ]</summary>

#### Checked Dependencies
  - org.springframework.boot:spring-boot-starter-parent:3.5.0
  - com.h2database:h2:2.3.232
  - com.mysql:mysql-connector-j:8.4.0
  - org.postgresql:postgresql:42.7.4
  - org.webjars:webjars-locator-lite:1.1.0
  - org.webjars.npm:bootstrap:5.3.6
  - org.webjars.npm:font-awesome:4.7.0
  - com.github.ben-manes.caffeine:caffeine:3.1.8

#### CVE issues
- Dependency `org.postgresql:postgresql` has **1** known CVEs, you must upgrade `org.postgresql:postgresql` to `42.7.7` or newer versions to fix them:
  - [CVE-2025-49146](https://github.com/advisories/GHSA-hq9p-pm7w-8p54): pgjdbc Client Allows Fallback to Insecure Authentication Despite channelBinding=require Configuration
    - **Severity**: **HIGH**
    - **Details**: ### Impact
      When the PostgreSQL JDBC driver is configured with channel binding set to `required` (default value is `prefer`), the driver would incorrectly allow connections to proceed with authentication methods that do not support channel binding (such as password, MD5, GSS, or SSPI  authentication). This could allow a man-in-the-middle attacker to intercept connections that users believed were protected by channel binding requirements.
      
      ### Patches
      TBD
      
      ### Workarounds
      
      Configure `sslMode=verify-full` to prevent MITM attacks.
      
      ### References
      
      * https://www.postgresql.org/docs/current/sasl-authentication.html#SASL-SCRAM-SHA-256
      * https://datatracker.ietf.org/doc/html/rfc7677
      * https://datatracker.ietf.org/doc/html/rfc5802



</details>


### ✅ Build project    [View Log](logs\11-buildProject.log)


### ✅ Summarize code changes    [View Log](logs\12-summarizeFixes.log)
1 file changed, 1 insertion(+), 0 deletions(-)
<details>
    <summary>[ click to toggle details ]</summary>

#### Code Changes
- Fix CVE-2025-49146 in PostgreSQL JDBC driver
  - Upgrade `org.postgresql:postgresql` to `42.7.7` to fix high-severity security vulnerability
  - Add explicit version property for PostgreSQL to override Spring Boot managed version



</details>


### ✅ Validate CVEs    [View Log](logs\13-validateCves.log)

<details>
    <summary>[ click to toggle details ]</summary>

#### Checked Dependencies
  - org.postgresql:postgresql:42.7.7



</details>


### ✅ Validate code behavior changes    [View Log](logs\14-validateBehaviorChanges.log)


### ✅ Run tests    [View Log](logs\15-runTests.log)

<details>
    <summary>[ click to toggle details ]</summary>

#### Test result
| Total | Passed | Failed | Skipped | Errors |
|-------|--------|--------|---------|--------|
| 56 | 54 | 0 | 2 | 0 |



</details>


### ✅ Summarize upgrading    [View Log](logs\16-summarizeUpgrading.log)

