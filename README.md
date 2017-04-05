# Ionic 2  Dial A Number

Access to **tel:*** is already present in the config.xml file for Ionic 2. If not you can allow access in the **config.xml** file by adding the following :

````
<access origin="tel:*" launch-external="yes"/>
````

in your **ts file** :

````
import ...

declare let window;

export class MoathdevPage {

call(mobile){
    //You can add some logic here
    mobile = encodeURIComponent(mobile);
     window.location = "tel:"+mobile;
    }
    
}    
````


As you can see we are using the **encodeURIComponent()** function. This will automatically convert the **#** to **%23.** Note that if try to cover the whole string **tel:+123#456-789** this will not work, so we are concatenating **"tel:"** with passed number.


