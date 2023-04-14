import pygame

# Define some colors
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
GRAY = (128, 128, 128)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
BLUE = (0, 0, 255)

# Define the dimensions of the warehouse
WIDTH = 800
HEIGHT = 600

# Initialize Pygame
pygame.init()

# Create a window
screen = pygame.display.set_mode((WIDTH, HEIGHT))

# Set the title of the window
pygame.display.set_caption("Warehouse")

# Define the positions and dimensions of the objects in the warehouse
cupboard1_rect = pygame.Rect(50, 50, 100, 200)
cupboard2_rect = pygame.Rect(250, 50, 100, 200)
cupboard3_rect = pygame.Rect(450, 50, 100, 200)
rack1_rect = pygame.Rect(50, 300, 200, 100)
rack2_rect = pygame.Rect(300, 300, 200, 100)
rack3_rect = pygame.Rect(550, 300, 200, 100)
table_rect = pygame.Rect(350, 450, 100, 100)

# Draw the objects in the warehouse
screen.fill(WHITE)
pygame.draw.rect(screen, GRAY, cupboard1_rect)
pygame.draw.rect(screen, GRAY, cupboard2_rect)
pygame.draw.rect(screen, GRAY, cupboard3_rect)
pygame.draw.rect(screen, GRAY, rack1_rect)
pygame.draw.rect(screen, GRAY, rack2_rect)
pygame.draw.rect(screen, GRAY, rack3_rect)
pygame.draw.rect(screen, BLUE, table_rect)

# Add some labels to the objects
font = pygame.font.Font(None, 30)
text = font.render("Cupboard 1", True, BLACK)
screen.blit(text, (cupboard1_rect.x, cupboard1_rect.y + cupboard1_rect.height + 10))
text = font.render("Cupboard 2", True, BLACK)
screen.blit(text, (cupboard2_rect.x, cupboard2_rect.y + cupboard2_rect.height + 10))
text = font.render("Cupboard 3", True, BLACK)
screen.blit(text, (cupboard3_rect.x, cupboard3_rect.y + cupboard3_rect.height + 10))
text = font.render("Rack 1", True, BLACK)
screen.blit(text, (rack1_rect.x, rack1_rect.y + rack1_rect.height + 10))
text = font.render("Rack 2", True, BLACK)
screen.blit(text, (rack2_rect.x, rack2_rect.y + rack2_rect.height + 10))
text = font.render("Rack 3", True, BLACK)
screen.blit(text, (rack3_rect.x, rack3_rect.y + rack3_rect.height + 10))
text = font.render("Table", True, BLACK)
screen.blit(text, (table_rect.x, table_rect.y + table_rect.height + 10))

# Update the screen
pygame.display.flip()

# Wait for the user to close the window
done = False
while not done:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            done = True

# Quit Pygame
pygame.quit()
