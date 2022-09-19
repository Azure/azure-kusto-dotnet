Kusto Client Library
====================

Updated documentation can be found at:
https://docs.microsoft.com/en-us/azure/kusto/api/netfx/about-kusto-data

What's new?
===========
Version 11.0.0 (19-SEP-2022)
* Kusto.Ingest: Upgrade Storage SDK to version 12
* Kusto HTTP Client: Fixed a bug where exception was thrown when using SetSocketOption in some operating systems

Version 10.1.1 (28-AUG-2022)
* Kusto.Ingest: Fixed a bug of a short timeout when uploading data to blob storage

Version 10.1.0 (24-JUL-2022)
* Kusto.Data: Fixed a bug where managed identity tokens were not cached leading to throttle errors when authenticating
* Kusto.Data: Fixed a bug where ClientRequestProperties properties were “lost” in some scenarios
* KustoConnectionStringBuilder: Fixed a bug where AzCli and AAD Managed Identity authentication methods were not working with Synapse clusters
* Kusto.Data: Fixed a bug where TCP keepalive timeouts were not correctly set
* Upgrade Newtonsoft.Json to version 13.0.1
* Kusto.Data: Rename WellKnownKustoEndpoints to KustoTrustedEndpoints

Version 10.0.3 (27-APR-2022)
* Kusto.Ingest: Fixed a bug to enable ingestion of publicly accessible blobs that are sent without a secret

Version 10.0.2 (12-APR-2022)
* Kusto.Ingest: Fixed a bug when ingesting blobs using Managed Identity credential notation URL

Version 10.0.1 (03-MAR-2022)
* Stable release of the last preview version

Version 10.0.0-preview (09-FEB-2022)
* Added support for .NET 5.0
* Kusto client (created via KustoClientFactory) was modified to prevent connecting to service URIs which are “unknown” over HTTPS, to protect the principal’s AAD token from being sent to unknown targets (this behaviour can be overriden by using Kusto.Data.Common.Impl.WellKnownKustoEndpoints.SetOverridePolicy)
* Kusto.Ingest: KustoStreamingIngestClient - improved blob ingestion flow
* Kusto HTTP client: Disable HTTP redirects by default, expose ExecuteRequestAsync
* KustoConnectionStringBuilder: Added support to provide Azure region on AAD SNI based application authentication
* KustoConnectionStringBuilder: Added new authentication methods - AAD device code authentication and Azure.Core.TokenCredential based authentication
* AAD managed identity based authentication: Support the same range of hosts supported by Azure.Identity.ManagedIdentityCredential
* Kusto.Ingest: Removed obsolete methods and associated descriptors
* Kusto.Ingest: Introduced IngestionTargetDefinition to initialize MultiTargetIngestClient

Version 9.4.1 (31-OCT-2021)
* Stable release of the last preview version

Version 9.4.0-preview (30-SEP-2021)
* KustoConnectionStringBuilder: Changed default value for the Streaming property to true
* Retargeted .NET Standard version to 2.0

Version 9.3.1 (10-AUG-2021)
* Kusto.Ingest: Extend IKustoQueuedIngestClient interface to allow providing an action that will be executed on every ingestion status notification processed from the notifications queue
* Upgrade MSAL to version 4.35.1

Version 9.3.0-preview (07-JUL-2021)
* Added dynamic authentication metadata resolution
* Kusto.Data: Added a new network client (KustoClientFactory.CreateKustoStatelessClient()) for proxy “fanout” scenarios
* Kusto.Ingest: Improved staging resources management
* Kusto.Ingest: Stopped compressing binary files when uploading to staging storage

Version 9.2.0 (25 APR 2021)
* Bug fix in Kusto HTTP client: Honor ExtendedServicePointManager.ServicePointCloudificationDisabled/ServicePointCloudificationDefaultConnectionLimit, if specified
* Bug fix in Kusto HTTP client: Properly shut down the connection pool on Dispose
* Upgrade MSAL to version 4.30.0

Version 9.1.0 (13 APR 2021)
* Kusto.Ingest: Introduce multi-target ingest clients, QueuedIngestMultiClient and StreamingIngestMultiClient, that are able to ingest the same data into more than a single target, on a best-effort basis
* Added ability to control the ConnectionLimit on outgoing connections to a Kusto cluster
* Fixed a bug preventing Kusto exceptions from being serializable
* KustoConnectionStringBuilder: Split AAD managed identity authentication into separate methods for system and user assigned identities
* KustoConnectionStringBuilder: AAD application subject name authentication will always attempt to load the most recently issued certificate

Version 9.0.9 (22 FEB 2021)
* Upgrade MSAL to version 4.27.0
* KustoConnectionStringBuilder: Support AAD login hint
* Improve handling of URIs with query parameters
* Kusto.Ingest: Storage operations performance improvements

Version 9.0.8 (26 JAN 2021)
* Upgrade MSAL to version 4.25.0

Version 9.0.7 (21 JAN 2021)
* Minor changes

Version 9.0.6 (10 JAN 2021)
* KustoConnectionStringBuilder: Add support for AzCli authentication
* Bug fixes and minor improvements

Version 9.0.5-preview (30 NOV 2020)
* Added support for .NET Standard 2.1
* Bug fixes

Version 9.0.4 (04 NOV 2020)
* AAD Subject Name and Issuer authentication: Added support for auto-rotation of expired certificates without the need to recreate the client and performance improvements
* Upgrade MSAL to version 4.22.0

Version 9.0.3 (15 OCT 2020)
* Upgrade MSAL to version 4.20.1
* Kusto.Ingest: Fixed a bug in serialization of IngestionStatus object

Version 9.0.1-preview (06 SEP 2020)
* Kusto.Ingest: Fixed a bug related to ingesting empty files

Version 9.0.0-preview (03 SEP 2020)
* Upgrade minimal .NET Framework version to 4.7.2 and .NET Core version to 2.1
* Migrate from Azure AD Authentication Library for .NET (ADAL.NET) to Microsoft Authentication Library for .NET (MSAL.NET)
* Kusto.Ingest: Expose DataReaderSourceOptions.MaxDegreeOfParallelism to limit the number of concurrent operations when writing IDataReader to blobs
* Kusto.Ingest: KustoManagedStreamingIngestClient - expose IKustoQueuedIngestClient to get status reporting from queue
* Kusto.Ingest: IKustoQueuedIngestClient - add methods to clear the status reporting queue
* Upgrade dSTS AL to version 3.0.2.405

Version 8.1.5 (26 JUL 2020)
* KustoConnectionStringBuilder: Support AAD application authentication based on subject name only

Version 8.1.4 (15 JUL 2020)
* Kusto.Data: Remove obsolete dependency on WindowsAzure.Storage

Version 8.1.3 (9 JUL 2020)
* Resolve running on Linux issues for .NET Core package
* Bug fixes

Version 8.1.2 (3 JUN 2020)
* Kusto.Ingest: Fix concurrency issue in KustoManagedStreamingIngestClient
* Minor bug fixes and improved diagnostics

Verison 8.1.1 (03 MAY 2020)
* KustoConnectionStringBuilder: Enhanced support for refeshing user-provided AAD tokens

Verison 8.1.0 (15 MAR 2020)
* Upgrade ADAL to version 5.2.7
* Ingest client local file size calculation improvements

Version 8.0.9 (04 MAR 2020)
* KustoConnectionStringBuilder: Support dSTS authentication against an explicity provided Security Token Service instance

Version 8.0.8 (04 FEB 2020)
* Bug fix for clusters using a single storage account

Version 8.0.7 (12 JAN 2020)
* Stability improvements and bug fixes
* Support for new data formats

Version 8.0.3 (24 NOV 2019)
* Performance improvements and bug fixes

Version 8.0.2 (14 NOV 2019)
* KustoConnectionStringBuilder: Support inline certificate for dSTS authentication

Version 8.0.1 (29 OCT 2019)
* KustoConnectionStringBuilder: Support refreshing user-provided AAD tokens without recreating clients

Version 8.0.0 (15 OCT 2019)
* Upgrade Newtonsoft.Json to version 12.0.2
* Upgrade ADAL to version 5.2.0
* Added obsolete attribute on old ingestion methods (IngestFromFile / IngestFromBlob)
* Bug fixes

Version 7.1.1 (24 JUL 2019)
* Fix System.Net.Http dll versioning issues

Version 7.1.0 (04 JUL 2019)
* Upgrade Newtonsoft.Json to version 11.0.2
* Upgrade dSTS AL to version 3.0.2.207

Version 7.0.1-preview (23 JUN 2019)
* Enhanced support for multi-regional resources

Version 7.0.0-preview (11 JUN 2019)
* Multiple bug fixes and performance improvements

Version 6.2.0-preview (02 APR 2019)
* Kusto.Ingest: Seal implementation classes that are not designed to be inheritable. Introduce adaptive storage management

Version 6.1.8 (24 MAR 2019)
* Upgrade ADAL's version to 4.5.1

Version 6.1.7 (03 MAR 2019)
* Support dSTS application authentication by subject name
* KustoManagedStreamingIngestClient: Support ingestion from storage and data reader. Fallback to queued ingestion when there are too many concurrent calls

Version 6.1.5 (18 FEB 2019)
* Fix bug that caused intermittent communication failures to permanently disable the ingest client

Version 6.1.4 (05 FEB 2019)
* Stable release of the last preview version

Version 6.1.2-preview (28 JAN 2019)
* Change for dynamic types of type scalar - IDataReader returned from ExecuteQuery / ExecuteControlCommand APIs will return scalar dynamic types as a JValue of the relevant scalar type, instead of returning the scalar type itself
* CslCommandGenerator: Stop supporting System.Int16, System.UInt16, System.UInt32, System.Byte and System.UInt64 types in table creation/alteration or merge commands
* Upgrade ADAL's version to 4.5.0
* Upgrade dSTS AL to version 3.0.2.182

Version 5.0.2 (04 DEC 2018)
* KustoConnectionStringBuilder: When authenticating using AAD application, authority id must be provided
* Diagnostic tracing improvements

Version 4.0.2-beta (05 AUG 2018)
* Use priority ranked resources in ingest client

Version 4.0.0 (19 JUL 2018)
* Upgrade WindowsAzure.Storage to version 9.3.0

Version 3.1.4 (15 JUL 2018)
* Bug fix: fix a memory leak when performing dSTS-based authentication.

Version 3.1.3 (09 JUL 2018)
* Better error messages for AAD Application authentication
* Support for overriding dSTS namespace expansion in app.config

Version 3.1.2 (17 JUN 2018)
* Upgrade ADAL's version from 3.19.4 to 3.19.8

Version 3.1.1 (10 JUN 2018)
* Introducing Kusto managed streaming ingest client

Version 3.1.0 (04 JUN 2018)
* Upgrade ADAL's version from 3.16.1 to 3.19.4 in order to support AAD application authentication by subject and issuer names (additional information: http://aadwiki/index.php?title=Subject_Name_and_Issuer_Authentication).
* Support dMSI-based authentication.

Version 3.0.20 (22 MAR 2018)
* Align version number with Kusto.Ingest library.

Version 3.0.19 (21 MAR 2018)
* Kusto.Cloud.Platform.Data.ExtendedDataReader: add support for writing collections to CSV files.

Version 3.0.18 (22 FEB 2018)
* Bug fixes and improvements.

Version 3.0.17 (1 FEB 2018)
* Include missing assemblies in package.

Version 3.0.15 (30 JAN 2018)
* Bug fixes: improve commands generation, improve exceptions phrasing

Version 3.0.14 (31 DEC 2017)
* New: Add support for decimal data type (using SqlDecimal).
* IDataReader implementation: Return "DBNull.Value" for null values, not "null as System.Object".

Version 3.0.9 (08 NOV 2017)
* Add support for EntityNotFoundException.

Version 3.0.8 (01 OCT 2017)
* Support explicit authority ID for AAD user authentication scenario.

Version 3.0.7 (13 SEP 2017)
* Fix hang when issuing multiple async requests requiring AAD authentication.

Version 3.0.6 (12 SEP 2017):
* Fix ADAL reference to version 3.16.1.

Version 3.0.5 (10 SEP 2017):
* Upgrade ADAL's version from 3.12.0 to 3.16.1

Version 3.0.4 (06 SEP 2017):
* Support Windows Hello for dSTS-based authentication (for Microsoft internal principals)

Version 3.0.3 (29 AUG 2017):
* CslCommandGenerator.GenerateExtentsDropByTagsCommand(): update to use a more efficient version of ExtentsShowCommand.

Version 3.0.2 (08 AUG 2017):
* Bug fix: Update Newtonsoft.Json dependency to version 10.0.3.

Version 3.0.1 (17 JULY 2017):
* Bug fix: Race condition in TraceSourceBase<> static construction.

Version 3.0.0 (05 JULY 2017):
* Upgrade Newtonsoft.Json to version 10.0.3 and Microsoft.WindowsAzure.Storage to version 8.1.4
* The client returns json errors instead of text errors.
* Client side is streaming.
* Dynamic values are encoded as json values and not strings.
* Boolean values may now be returned as Booleans instead of numbers.
* Strongly-typed clients based on ObjectReader return JSON.NET objects.

Version 2.5.12 (28 JUNE 2017):
* Bug fix - NullReference in RestClient2

Version 2.5.11 (28 JUNE 2017):
* Bug fix - using ClientRequestProperties.Application/UserName should override KustoConnectionStringBuilder.ApplicationNameForTracing/UserNameForTracing.

Version 2.5.10 (20 JUNE 2017):
* Bug fix - fix hang when running inside 'Orleans' framework

Version 2.5.9 (15 JUNE 2017):
* NetworkCache: Added support for setting timer start refreshing time and cache refreshing timeout.

Version 2.5.8 (08 JUNE 2017):
* Kusto.Cloud.Platform.Data.ObjectReader<T>: Added support for fields of type JToken (or derived).

Version 2.5.7 (22 MAY 2017):
* KCSB - block sending corporate credentials when using basic authentication

Version 2.5.6 (21 MAY 2017):
* Bug fix in ExecuteStreamIngestAsync - fix behavior of mappingName parameter

Version 2.5.5 (18 MAY 2017):
* Bug fix (null ref when runnin in Mono).

Version 2.5.4 (7 MAY 2017):
* Extend kusto ingestion error codes with 'NoError'.

Version 2.5.3 (27 APR 2017):
* Add kusto ingestion error codes.

Version 2.5.2 (09 APR 2017):
* Bug fix - support AAD token acquisition based-on application client ID and certificate thumbprint.

Version 2.5.1 (30 MAR 2017):
* Add Kusto Connection String validation.

Version 2.5.0 (16 MAR 2017):
* Target client library to .net 4.5 to enable customers that cannot use higher versions to use Kusto client.

Version 2.4.9 (13 FEB 2017):
* Support AAD Multi-Tenant access to Kusto for applications.

Version 2.4.8 (12 FEB 2017):
* Support AAD Multi-Tenant access to Kusto.

Version 2.4.7 (31 JAN 2017):
* Kusto clients version alignment.

Version 2.4.6 (24 DEC 2016):
* Fixing a bug in CslCommandGenerator's GenerateTableExtentsShowCommand().

Version 2.4.5 (24 NOV 2016):
* Extend Azure Storage retry policy in order to handle IO exceptions.

Version 2.4.4 (16 NOV 2016):
* Extend Azure Storage retry policy in order to handle web and socket exceptions.

Version 2.4.3 (16 NOV 2016):
* Support Multi-Factor Authentication enforcement for AAD-based authentication.

Version 2.4.2 (22 SEP 2016):
* Fix potential deadlock in 'ExecuteQuery' when running in IIS.

Version 2.4.1 (20 SEP 2016):
* Fix potential deadlock during AAD token acquisition.

Version 2.4.0 (19 SEP 2016):
* Security bug fix (client credentials leak to traces).

Version 2.3.9 (5 SEP 2016):
* Support dSTS-based application authentication.

Version 2.3.8 (12 AUG 2016):
* Target client library to .net 4.5 to enable customers that cannot use higher versions to use ksuto client.

Version 2.3.7 (12 AUG 2016):
* Fix issue where null pointer exceptions are thrown for client on syntax errors rather than a meaningful error
* Make ExecuteQueryAsync async all the way down incl. 3rd party libraries (ADAL).

Version 2.3.5 (24 JUL 2016):
* Fix UI potential deadlock during AAD token acquisition.

Version 2.3.4 (20 JUL 2016):
* Upgrade ADAL's version from 2.14.2011511115 to 3.12.0

Version 2.3.3 (19 JUL 2016):
* Supporting dSTS-based authentication for Microsoft internal principals. More details can be found at https://kusto.azurewebsites.net/docs/concepts/concepts_security_authn_dsts.html.