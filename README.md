# opencv-basics
import cv2
import numpy as np
cap=cv2.imread('index5.png',1)
hsv = cv2.cvtColor(cap, cv2.COLOR_BGR2HSV)
lower_blue=np.array([110,50,50])
upper_blue=np.array([130,255,255])
mask=cv2.inRange(hsv,lower_blue,upper_blue)
res = cv2.bitwise_and(cap,cap, mask= mask)
cv2.imshow('frame',cap)
cv2.imshow('mask',mask)
cv2.imshow('res',res)
k = cv2.waitKey(0)
if k == 27:         # wait for ESC key to exit
    cv2.destroyAllWindows()
elif k == ord('s'): # wait for 's' key to save and exit
    cv2.imwrite('index5.png',img)
    cv2.destroyAllWindows()
