# Text Recognition from Image using Mobile Vision API in Android

> Develop android application to recognise Text from Image using Mobile Vision API.

![Image for post](https://miro.medium.com/max/28/1*of40W-Yv-Jo3q-QX37rVAg.png?q=20)

![Image for post](https://miro.medium.com/max/2160/1*of40W-Yv-Jo3q-QX37rVAg.png)

Sample Image

![Image for post](https://miro.medium.com/max/2130/1*xBLaf6nxkhrEa8-RXKwy4Q.jpeg)

Output of Mobile vision

Introduction to Mobile Vision
-----------------------------

Mobile Vision is powerful API available in most Android devices. Some use-cases of Mobile Vision are 1. Detect faces 2. Barcode scanner 3. Text recognition. In this post we are developing android application for text recognition using Mobile Vision.

Use cases of Text Recognition
-----------------------------

1.  Extracting Invoices parameters from Invoice and Bills
2.  Digitising documents
3.  Scanning vouchers, cards and etc.

Text Recognition Mobile Vision
------------------------------

Mobile Vision API segments text into three parts; Blocks, Lines, and words.

![Image for post](https://miro.medium.com/max/3532/1*ukvZg9kDbGNdJlHh6UC3BQ.png)

Souce: [https://developers.google.com/vision/android/text-overview](https://developers.google.com/vision/android/text-overview)

Github repo :

Tutorial
--------

1.  Start new project. Select empty activity and give preferred to the project.
2.  Go to Gradle scripts. In build.gradle( Module :app we have to add dependencies for given project). Since we are using Google mobile vision api we have to add its dependancies. Add line : implementation **‘com.google.android.gms:play-services-vision:19.0.0’**

dependencies {  
    implementation fileTree(**dir**: **'libs'**, **include**: \[**'\*.jar'**\])  
    implementation **'androidx.appcompat:appcompat:1.1.0'** implementation **'androidx.constraintlayout:constraintlayout:1.1.3'** testImplementation **'junit:junit:4.12'** androidTestImplementation **'androidx.test.ext:junit:1.1.1'** androidTestImplementation **'androidx.test.espresso:espresso-core:3.2.0'**implementation **'com.google.android.gms:play-services-vision:19.0.0'  
**}

3\. Get camera permission from Manifest file

<**uses-feature  
    android:name="android.hardware.camera"  
    android:required="true"** />

4\. Layout file:

<**LinearLayout  
    android:layout\_width="match\_parent"  
    android:layout\_height="match\_parent"  
    android:orientation="vertical"**\>  
<**Button  
    android:id="@+id/btn"  
    android:layout\_width="match\_parent"  
    android:layout\_height="wrap\_content"  
    android:layout\_margin="20dp"  
    android:text="Start the camera"** />

<**ImageView  
    android:id="@+id/imageView"  
    android:layout\_width="wrap\_content"  
    android:layout\_height="wrap\_content"  
    android:layout\_margin="20dp"  
    android:visibility="visible"  
    tools:srcCompat="@tools:sample/avatars"** />

<**TextView  
    android:id="@+id/text"  
    android:layout\_width="match\_parent"  
    android:layout\_height="wrap\_content"  
    android:layout\_alignParentBottom="true"  
    android:layout\_margin="20dp"  
    android:textColor="#000000"  
    android:textSize="20sp"** />  
</**LinearLayout**\>

4\. MainActivity file, recogniser

**recognizer**\=  **new** TextRecognizer.Builder(getApplicationContext()).build();

**if**(**recognizer**.isOperational())  
{  
   _// bitmap.;_ Frame frame =**new** Frame.Builder().setBitmap(**bitmap**).build();

    **final** SparseArray<TextBlock> items = **recognizer**.detect(frame);  
    **if** (items.size() != 0)  
    {  
        StringBuilder stringBuilder = **new** StringBuilder();  
        **for** (**int** i=0 ; i<items.size(); i++)  
        {  
            TextBlock item = items.valueAt(i);  
            stringBuilder.append(item.getValue());  
            stringBuilder.append(**"\\n"**);  
        }  
        **textView**.setText(stringBuilder.toString());  
    }  
}

Github Repository

Download sample application

I am writing at pandemic time of COVID19. Hope you are doing well. Stay SAFE. Stay HEALTHY. Let’s utilise this time for learning new, reading books, or something constructive. Hit clap if you like this post.Thanks for reading.


[Source](https://shreeshivpatel.medium.com/text-recognition-from-image-using-mobile-vision-api-in-android-b604f433e2c4)