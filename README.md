# App-using-the-phones-sensors
Many Android-powered devices include built-in sensors that measure motion, orientation, and environmental conditions such as ambient light or temperature. These sensors can provide data to your app with high precision and accuracy. Sensors can be used to monitor three-dimensional device movement or positioning, or to monitor changes in the environment near a device, such as changes to temperature or humidity. For example, a game might track readings from a device's accelerometer sensor to infer complex user gestures and motions, such as tilt, shake, or rotation.






*Create an app that lists the available device sensors.
Run the app on a device and on the emulator to view sensors.
Create a second app that gets data from the light and proximity sensors, and displays that data.
Interact with the device and note the changes in sensor data.
Run the app in the emulator and learn about the emulator's virtual sensors.*


To use the sensors in the app that the users phone has you have to *get the sensors*
1)you modify the activity's onCreate() method to gain access to the light and proximity sensors.
2)Open MainActivity and add private member variables at the top of the class to hold Sensor objects for the light and proximity sensors. Also add private member variables to hold the TextView objects from the layout
example:// Individual light and proximity sensors. 
private Sensor mSensorProximity;
private Sensor mSensorLight;

// TextViews to display current sensor values   
private TextView mTextSensorLight;
private TextView mTextSensorProximity;

If you want andriod to change the data based on new data you have to add a "SensorEvent"
1)modify the class signature to implement the SensorEventListener interface.
2)The SensorEventListener interface includes two callback methods that enable your app to handle sensor events:

onSensorChanged(): Called when new sensor data is available. You will use this callback most often to handle new sensor data in your app.
onAccuracyChanged(): Called if the sensor's accuracy changes, so your app can react to that change. Most sensors, including the light and proximity sensors, do not report accuracy changes. In this app, you leave onAccuracyChanged() empty.
Override the onStart() activity lifecycle method to register your sensor listeners. Listening to incoming sensor data uses device power and consumes battery life. Don't register your listeners in onCreate(), as that would cause the sensors to be on and sending data (using device power) even when your app was not in the foreground. Use the onStart() and onStop() methods to register and unregister your sensor listeners.

After everything is set up you can then run the emulator and play around with the virtual sensors in the extended controls.
