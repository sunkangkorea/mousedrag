import cv2
import numpy as np

drawing = False
ix, iy = -1, -1
num_x = 2
num_y = 2

def draw_ellipse(event, x, y, flags, param):
    global ix, iy, drawing, num_x, num_y
    if event == cv2.EVENT_LBUTTONDOWN:
        drawing = True
        ix, iy = x, y
    elif event == cv2.EVENT_MOUSEMOVE:
        if drawing == True:
            img.fill(0)
            cv2.ellipse(img, (ix + (x - ix)//2, iy + (y - iy)//2), (abs(x - ix)//num_x, abs(y - iy)//num_y), 0, 0 , 360, (0,255,0), 1)
    elif event == cv2.EVENT_LBUTTONUP:
        drawing = False
        cv2.ellipse(img, (ix + (x - ix)//2, iy + (y - iy)//2), (abs(x - ix)//num_x, abs(y - iy)//num_y), 0, 0 , 360, (0,255,0), 1)

img = np.zeros((512,512,3), np.uint8)
cv2.namedWindow('image')
cv2.setMouseCallback('image', draw_ellipse)

while True:
    cv2.imshow('image', img)
    if cv2.waitKey(1) == 27: # 27번 키 == ESC키
        break

cv2.destroyAllWindows()
