# Migration guide from API v.1.6 to v.1.7

```
This is working draft of migration guide. Please wait for an official announcement for switching to this API version
```
## Feature support changes

- Removal of file hosting support. All content is now hosted on appdb.
- Removal of Direct Installation support and FairPlay Direct installation support.
- Removal of appsync configuration.
- Addition of lots of APIs related to official app publication.
- Introduction of App Enhancements APIs instead of Dylib libraries APIs.
- Introduction of copyright violation reporting APIs.
- Introduction of installation history instead of IPA cache.

## API changes

### Specification

Updated specification is located at [this URL](https://api.dbservices.to/v1.7/spec/).

### Replaced methods

- **search_index** - use instead search
- **universal_gateway** - use instead search to get content details
- **add_enhancement** - use instead of add_dylib
- **get_enhancements** - use instead of get_dylibs
- **get_enhancement_analyze_jobs** - use to track enhancement addition process to user library
- **delete_enhancement** - use instead of delete_dylib
- **get_install_history** - use instead of get_ipa_cache_status
- **edit_ipa_metadata** - use instead edit_content_metadata

### Deleted methods

- **search**
- **get_links**
- **add_dylib**
- **delete_dylib**
- **ensure_ipa_cache**
- **install_from_cache**
- **get_content_requirements**
- **submit_links**
- **edit_content_metadata**
- **get_protection_validation_id**
- **delete_ipa_from_cache**
- **transfer_ipa_cache**
- **clear_ipa_cache**
- **report**

### Changed methods
- **install** - added universal object identifier support, deleted types ios, cydia, tvos, osx, standalone. Deleted FairPlayDirectInstallation support. Deleted protection_validation_id requirement.
- **configure**, **get_configuration**, **get_all_devices** - deleted appsync
- **list_genres** - deleted all types except official
- **set_publish_request_status** - removal of IPA submission, addition of setting of publicly available universal object identifier as a fulfillment result
