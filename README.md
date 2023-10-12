# thredds-data-server-config
Code related to configuring the thredds data server (crocus-server-03.cels.anl.gov)

## How to Expose New Datastreams on the THREDDS Server

### Modify the `catalog.xml` file
Once you have your netCDF datasets ready to publish, go to the `/data/home/thredds/catalog.xml` file, and add a new entry following the xml format:

```xml
<dataset name="Doppler Lidar">
    <metadata inherited="true">
      <serviceName>all</serviceName>
      <dataType>POINT</dataType>
      <documentation>Doppler Lidar</documentation>
    <keyword>Vertical</keyword>
    <date type="created">2023</date>
    </metadata>
    <datasetScan name="Northeastern Illinois Doppler Lidar" ID="neiu-dopplerlidar-a1"
                 path="neiu-dopplerlidar-a1" location="/data/datastream/neiu/neiu-dopplerlidar-a1" dataType="Point">
      <metadata inherited="true">
       <serviceName>all</serviceName>
      </metadata>
      <addLatest/>
    </datasetScan>
  </dataset>
```

### Restart the Server
You will need to admin access to restart the server. If you do not have admin access, please contact Max Grover (mgrover@anl.gov) to request a THREDDS server restart.

```
./usr/local/tomcat/bin/shutdown.sh
./usr/local/tomcat/bin/startup.sh
```
