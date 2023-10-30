# gooddata-simple-uploader

meltano project created for the purpose of loading CSV data from S3 (or local files) into Snowflake
and then further on to the gooddata

```shell
# 1. / add the extractor
meltano add extractor tap-csv
meltano invoke tap-csv --discover  # verify data ingesting works fine
meltano config tap-csv  # verify configuration
meltano select tap-github --list --all  # select what to extract
# 2. / add the loader
meltano add loader target-snowflake
meltano invoke target-snowflake --initialize
```
