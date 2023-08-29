import pygame
import random

# Initialize Pygame
pygame.init()

# Set up display
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Action RPG Game")

# Colors
white = (255, 255, 255)
black = (0, 0, 0)

# Player attributes
player_x = screen_width // 2
player_y = screen_height - 50
player_speed = 5

# Main game loop
running = True
clock = pygame.time.Clock()

while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
        player_x -= player_speed
    if keys[pygame.K_RIGHT]:
        player_x += player_speed
    if keys[pygame.K_UP]:
        player_y -= player_speed
    if keys[pygame.K_DOWN]:
        player_y += player_speed

    screen.fill(white)
    pygame.draw.rect(screen, black, (player_x, player_y, 50, 50))

    pygame.display.flip()
    clock.tick(60)

pygame.quit()
