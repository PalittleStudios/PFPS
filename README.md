# PFPS: Palittle First Person Shooter Library

PFPS is a Python library for FPS game development, featuring tools for importing sounds, 3D models, and images, as well as gameplay mechanics and rendering utilities.

# Example Code:


import pygame
import pywavefront
from PIL import Image
from pfps.audio import load_sound, play_sound
from pfps.models import load_model
from pfps.images import load_image
from pfps.gameplay import Player
from pfps.render import init_screen, draw_object

# Initialize game screen
screen = init_screen(800, 600)

# Load and play background sound
sound = load_sound("background.wav")
play_sound(sound)

# Load 3D model (character)
model = load_model("character.obj")

# Load and display texture image
image = load_image("texture.png")
if image:
    resized_image = image.resize((128, 128))
    resized_image.show()  # Opens the image in the default image viewer

# Create and move player
player = Player("Palittle", 100, [100, 100])
player.move("forward")
player.shoot()

# Draw a simple object on the screen
draw_object(screen, (255, 0, 0), [300, 300], [50, 50])

# Keep the window open
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

pygame.quit()




## Installation
```bash
pip install PFPS
