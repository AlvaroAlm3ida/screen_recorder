# screen_recorder
📹 Criando um Gravador de Tela Usando Python!
Você já pensou em construir seu próprio gravador de tela com Python? Aqui está uma maneira simples de fazer isso utilizando bibliotecas poderosas como pyautogui e OpenCV! 🔥

Como funciona?
📸 Captura de tela contínua com pyautogui.
🎥 Manipulação de vídeo usando OpenCV para armazenar as capturas como um arquivo MP4.
⚙️ Configuração fácil de resolução, FPS e codec.

🔧 Ferramentas:
pyautogui: Para capturar a tela.
cv2 (OpenCV): Para manipular e salvar o vídeo.

Veja o código para começar:

import pyautogui
import cv2
import numpy as np

resolution = (1920, 1080)
codec = cv2.VideoWriter_fourcc(*"CLCO")
filename = "Recording.mp4"
fps = 60.0
out = cv2.VideoWriter(filename, codec, fps, resolution)
cv2.namedWindow("Live", cv2.WINDOW_NORMAL)
cv2.resizeWindow("Live", 480, 370)

while True:
 img = pyautogui.screenshot()
 frame = np.array(img)
 frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
 out.write(frame)
 cv2.imshow('Live', frame)
 if cv2.waitKey(1) == ord('q'):
 break

print("Screen Recording started")
out.release()
cv2.destroyAllWindows()

Esse código permite capturar sua tela em tempo real e salvar em um vídeo MP4!
