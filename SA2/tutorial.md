Display the Data on Node-RED
======================
In this activity, you will display the maximum g-force on Node-RED.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/11110387/pasted-from-clipboard.png" width = "100%" height = "50%">




Follow the given steps to complete this activity.




1. Store the acceleration by getting the acceleration from the three axes.


    ~~~cpp
        float accx = acc.acceleration.x/10;
        float accy = acc.acceleration.y/10;
        float accz = acc.acceleration.z/10;
    ~~~


2. Find the maximum acceleration by comparing the acceleration from the three axes.


    ~~~cpp
        float maxGforce = fmax(fmax(fabs(accx), fabs(accy)), fabs(accz));
    ~~~


3. Publish the g-force by publishing the maximum g-force as the new topic.
    ~~~cpp
        String gforceStr = String(maxGforce, 1);


        client.publish("/Gforce",gforceStr.c_str());
    ~~~
* open Node-RED by typing `node-red` in the command prompt.
4. Add and configure one mqttin, one gauge, one chart and one debug widget to the Node-RED flow.


    <img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/11110491/pasted-from-clipboard.png" width = "70%" height = "50%">


5. Display the payload on the debug screen and the g-force on the dashboard by deploying the flow.


    <img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/11110387/pasted-from-clipboard.png" width = "70%" height = "50%">




* Save and run the code to check the output.
