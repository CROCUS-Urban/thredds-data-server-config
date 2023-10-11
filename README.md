# thredds-data-server-config
Code related to configuring the thredds data server

## How to Add New Datastreams
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
