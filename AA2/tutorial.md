Display the Rotation Data
======================
In this activity, you will display the rotation data received from the sensor on the Node-RED dashboard.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/11143934/AA2.gif" width = "100%" height = "50%">




Follow the given steps to complete this activity.




1. Save the gyroscope data in gccx, gccy, gccz
* Open the `sketch.ino` file on `Wokwi`.
    ~~~cpp
        float gccx = gcc.gyro.x * 250/4.36;
        float gccy = gcc.gyro.y * 250/4.36;
        float gccz = gcc.gyro.z * 250/4.36;
    ~~~
2. Find the maximum rotation.
    ~~~cpp
    float maxRotation = fmax(fmax(fabs(gccx),fabs(gccy)),fabs(gccz));
    ~~~
3. Save string value of maxRotation in rotationStr and publish it.
    ~~~cpp


    String rotationStr = String(maxRotation, 1);
    client.publish("/Rotation", rotationStr.c_str());
    ~~~


* Save and run the code to check the output.
* Open node-red dashboard to view the alert on the dashboard.
