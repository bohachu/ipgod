# ipgod

### Create database and table
```SQL
CREATE TABLE ckan_download (
	package_name    CHAR(17) NOT NULL,
	file_id         CHAR(3)  NOT NULL, 
	download_time   TIMESTAMP WITH TIME ZONE,
	status          SMALLINT,
	processed       boolean, 
	PRIMARY KEY(package_name, file_id)
);
```

### Install required modules first.
```bash
$ pip install schedule requests PyGreSQL
```

###Change configuration in config.py
```python
FetchHistory=True # start a thread to get history data since last update

db_ip = "localhost"         # IP of Database which having download status 
db_port=5432                # Port of Database which having download status 
db_user="ckan_default"      # username of Database which having download status 
db_password="ckan_passwd"   # password of Database which having download status
 
DOWNLOAD_PATH = '/tmp'      # Where to place download open data resource
```

