# domashka2
from pygame import *

window = display.set_mode((700, 500))
display.set_caption("Доганялки")

background = transform.scale(image.load('background.png'), (700, 500))

sprite1 = transform.scale(image.load('sprite1.png'), (80, 80))
sprite2 = transform.scale(image.load('sprite2.png'), (80, 80))

x1 = 100
y1 = 400

x2 = 410
y2 = 290

clock = time.Clock()
start = True
while start == True:
    for e in event.get():
        if e.type == QUIT:
            start = False
    window.blit(background, (0, 0))

    window.blit(sprite1, (x1, y1))
    window.blit(sprite2, (x2, y2))

    all_keys = key.get_pressed()
    if all_keys[K_w] and y1 > 5:
        y1 -= 5
    if all_keys[K_s] and y1 < 415:
        y1 += 5
    if all_keys[K_d] and x1 < 615:
        x1 += 5
    if all_keys[K_a] and x1 > 5:
        x1 -= 5

        all_keys = key.get_pressed()
    if all_keys[K_UP] and y2 > 5:
        y2 -= 5
    if all_keys[K_DOWN] and y2 < 415:
        y2 += 5
    if all_keys[K_RIGHT] and x2 < 615:
        x2 += 5
    if all_keys[K_LEFT] and x2 > 5:
        x2 -= 5


    display.update()
    clock.tick(60)
