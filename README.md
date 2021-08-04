# Real-time-Face-detection-by-OpenCV
this repository shows the steps taken to Run Real-time Face detection by OpenCV.

These were tested under Windows 10 .

# Dependencies

**1.Download python program**

Python 3.6.4 installation Website link : https://www.python.org/downloads/ 

It is important to specify the two conditions to avoid problems


![70](https://user-images.githubusercontent.com/86648269/128063092-5f536844-7a8a-47fd-bd12-16458630b560.png)


Then  press Custom

![71](https://user-images.githubusercontent.com/86648269/128063115-19526ca3-8ae2-485f-9d43-0825ad5cdf70.png)

Then select all the Python packages

![72](https://user-images.githubusercontent.com/86648269/128063139-e1ce9365-a5c4-4ed6-beb2-b08056f1b96f.png)

![73](https://user-images.githubusercontent.com/86648269/128063301-654351a9-5543-400e-8fac-8ac000f7ad13.png)


**2.Download OpenCV**

By typing commands in terminal

```

pip install opencv-python


```

**3.Uploaded Face Detect file**


**4.Run the code below in PyCharm**

```
import cv2

cap = cv2.VideoCapture(0)
cascade_classifier = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')

while True:

    ret, frame = cap.read()
    gray = cv2.cvtColor(frame, 0)
    detections = cascade_classifier.detectMultiScale(gray, scaleFactor=1.3, minNeighbors=5)

    if(len(detections) > 0 ):
        (x, y, w, h) = detections[0]
        frame = cv2.rectangle(frame, (x,y), (x+w, y+h), (255,0,0), 2)

    cv2.imshow('frame', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()

```


  **6.Results** 
  
  ![74](https://user-images.githubusercontent.com/86648269/128072430-b770934f-8faf-4118-90bc-a86a24a5e925.png)


![75](https://user-images.githubusercontent.com/86648269/128072439-4aabf16e-4e8c-4a8d-adc8-51d52868f1b4.png)


