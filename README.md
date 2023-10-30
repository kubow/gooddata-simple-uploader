# gooddata-simple-uploader

[meltano](https://docs.meltano.com/getting-started/part1/) project created for the purpose of loading CSV data from S3 (or local files) into Snowflake
and then further on to the gooddata

```shell
# 0. / prepare envrionment
python -m venv venv  # init directory
source venv/bin/activate  # activate environment
pip install -r requirements.txt  # install dependencies
meltano init my-meltano-project
# 1. / add the extractor
meltano add extractor tap-csv
meltano invoke tap-csv --discover  # verify data ingesting works fine
meltano config tap-csv  # verify configuration
meltano select tap-github --list --all  # select what to extract
# 2. / add the loader
meltano add loader target-snowflake
meltano invoke target-snowflake --initialize
```
