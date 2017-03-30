# Docker for ThingWorx Analytics Builder

## Usage

Copy Thingworx war file and license file.
```
$ cp <PATH TO>/Thingworx.war ./Thingworx
$ cp <PTAH TO>/license.bin ./Thingworx
```

Copy UploadThing
```
$ cp <PATH TO>/UploadThing_Install-1.2.zip  ./UploadThing/UploadThing_Install.zip
```

Copy ThingPredictor
```
$ cp <PATH TO>/prediction-with-analysis.yml ./ThingPredictor
$ cp <PATH TH>/thingpredictor.jar ./ThingPredictor
```

Build docker image
```
$ docker-compose build
```

Start ThingWorx
```
$ docker-compose up -d
```

Import ThingWorx ANalytics Extension

Stop ThingWorx
```
$ docker-conpose down
```



