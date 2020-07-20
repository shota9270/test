# test
import matplotlib as mpl
mpl.use('Agg')
import matplotlib.pyplot as plt
import cv2
import numpy as np

x = [100, 200, 300, 400, 500, 600]
y = [10, 20, 30, 100, 120, 130]
y1 = [10, 20, 30, 50, 80, 130]


plt.figure(figsize=(4,7))
plt.plot(x,y)
plt.savefig("hoge.png")

plt.figure(figsize=(4,7))
plt.plot(x, y1);
plt.savefig("fuge.png")

img1 = cv2.imread('hoge.png',1)
img2 = cv2.imread('fuge.png',1)

comparison=np.where(img1 == img2, 0, 1)

difference=np.array(img1*comparison)

cv2.imwrite('difference.png',difference)
