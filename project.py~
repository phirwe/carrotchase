import pygame
from pygame.locals import *
import random

icon = pygame.image.load("bunny1.png")
pygame.display.set_icon(icon)
pygame.init()
class Bunny:
	def __init__(self, surface, x, y,filename):
		 self.surface = surface
		 self.im = pygame.image.load(filename)
		 self.x = x
		 self.y = y
		 self.dir_x = 0
		 self.dir_y = 0
		 #self.crashed = False
	def key_event(self, event):
		 if event.key == pygame.K_UP:
		     self.dir_x = 0
		     self.dir_y = -1
		 elif event.key == pygame.K_DOWN:
		     self.dir_x = 0
		     self.dir_y = 1
		 elif event.key == pygame.K_LEFT:
		     self.dir_x = -1
		     self.dir_y = 0
		 elif event.key == pygame.K_RIGHT:
		     self.dir_x = 1
		     self.dir_y = 0
	def move(self):
		 self.x += self.dir_x
		 self.y += self.dir_y
	def draw(self):	
		screen.blit(self.im,(self.x, self.y))
	def write(self, surface, text, text_color, length, height, x, y,size):
		self.background = pygame.Surface(screen.get_size())
		font = pygame.font.Font(None, size)
		text = font.render(text, 1, text_color)
		surface.blit(text, ((x+length/2) - text.get_width()/2, (y+height/2) - text.get_height()/2))
		return text
	def create_button(self, surface, color, x, y, length, height, text, text_color,size):
		pygame.draw.rect(surface, color, (x,y,length,height), 0)
        	pygame.draw.rect(surface, (190,190,190), (x,y,length,height), 1)
		surface = self.write(surface, text, text_color, length, height, x, y,size)
		self.rect = pygame.Rect(x,y, length, height)
		return surface
	def pressed(self, mouse):
         if mouse[0] > self.rect.topleft[0]:
            if mouse[1] > self.rect.topleft[1]:
                if mouse[0] < self.rect.bottomright[0]:
                    if mouse[1] < self.rect.bottomright[1]:
                        #print "Some button was pressed!"
                        return True
                    else: return False
                else: return False
            else: return False
         else: return False
# Dimensions.
pickUpSound = pygame.mixer.Sound('bite.wav')
width = 640 
height = 400
pygame.init()
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Carrot Chase")
clock = pygame.time.Clock()
foodi = pygame.image.load('carrot.png')#cherry
end = pygame.image.load('home.png')#house
f = open('add.txt')
fsub=open('subtraction.txt')
lsub = fsub.readlines()
l = f.readlines()
f.close()
fsub.close()
f1 = open('answers.txt')
f1sub=open('answer.txt')
l1sub = f1sub.readlines()
l1 = f1.readlines()
f1.close()
f1sub.close()
playing = 0
points = 0
one = 0
next = 0
running = 0
w = Bunny(screen, width/2, height/2,'bunny1.png')
def inst(k,z):
	while z :
		screen.fill((0,0,0))
		text =k.write(screen, "HOW TO PLAY:", (0,0,190), width, height-80, 0,-100,50)
		text =k.write(screen, "1.You are given two options:", (0,0,190), width/2, height, 0,-100,35)
		text = k.write(screen, "2.Choose one of them to start playing.", (0,0,190), 20+width/2, height+40, 0,-100,35)
		text = k.write(screen, "3.The question is displayed and click on Play.", (0,0,190), 40+width/2, height+80, 0,-100,35)
		text = k.write(screen, "4.Collect the carrots according to your answer.", (0,0,190), 60+width/2, height+120, 0,-100,35)
		text = k.write(screen, "5.You can undo recent moves.", (0,0,190), 10+width/2, height+160, 0,-100,35)
		text = k.write(screen, "6.After you are done, guide the rabbit to his house", (0,0,190), width/2, height+200, 0,-100,35)
		text = k.write(screen, "7.You get 10 points for the right answer.", (0,0,190), width/2, height+240, 0,-100,35)
		x = k.create_button(screen, (107,142,35), (width-100), (height-50), 100, 50, "Home", (255,255,255),20)
		for event in pygame.event.get():
					if event.type == pygame.MOUSEBUTTONDOWN:
						if k.pressed(pygame.mouse.get_pos()):
							z = start(k)
						
		pygame.display.flip()
		clock.tick(200)
def start(m):
       while 1 :
	screen.fill((0, 0, 0))
	text = m.write(screen, "CARROT CHASE", (0,0,190), width, height, 0,-100,75)
	b = m.create_button(screen, (200,200,200), (width-100)/2, (height-50)/2, 100, 50, "ADDITION", (0,0,0),20)
	b1 = m.create_button(screen, (200,200,200), (width-100)/2, (height+80)/2, 100, 50, "SUBTRACTION", (0,0,0),18)
	b2 = m.create_button(screen, (200,200,200), (width-100)/2, (height+200)/2, 100, 50, "INSTRUCTIONS", (0,0,0),18)
	for event in pygame.event.get():
				if event.type == pygame.MOUSEBUTTONDOWN:
					lis = pygame.mouse.get_pos()
					if lis[0] > (width-100)/2 and lis[0] < ((width-100)/2 + 100):
						if lis[1] > (height-50)/2 and lis[1] < ((height-50)/2 + 50):
							return 1
					if lis[0] > (width-100)/2 and lis[0] < ((width-100)/2 + 100):
						if lis[1] > (height+80)/2 and lis[1] < ((height+80)/2 + 50):
							return 2
					if lis[0] > (width-100)/2 and lis[0] < ((width-100)/2 + 100):
						if lis[1] > (height+200)/2 and lis[1] < ((height+200)/2 + 50):
							s = 1
							while s :
								k = m
								screen.fill((255,200,200))
								text =k.write(screen, "HOW TO PLAY:", (0,0,0), width, height-80, 0,-100,50)
								text =k.write(screen, "1.You are given two options:", (0,0,190), (width/2)+10, height, 0,-100,35)
								text = k.write(screen, "2.Choose one of them to start playing.", (0,0,190), 120+width/2, height+60, 0,-100,35)
								text = k.write(screen, "3.The question is displayed and click on Play.", (0,0,190), 210+width/2, height+120, 0,-100,35)
								text = k.write(screen, "4.Collect the carrots according to your answer.", (0,0,190),220+width/2, height+180, 0,-100,35)
								text = k.write(screen, "5.You can undo recent moves.", (0,0,190), 30+width/2, height+240, 0,-100,35)
								text = k.write(screen, "6.After you are done, guide the rabbit to his house", (0,0,190), 260+width/2, height+300, 0,-100,35)
								text = k.write(screen, "7.You get 10 points for the right answer.", (0,0,190), 140+width/2, height+360, 0,-100,35)
								x = k.create_button(screen, (200,200,200), (width-100), (height-50), 100, 50, "Home", (0,0,0),20)
								for event in pygame.event.get():
											if event.type == pygame.MOUSEBUTTONDOWN:
												if k.pressed(pygame.mouse.get_pos()):
													s = 0
						
								pygame.display.flip()
								clock.tick(200)
				elif event.type == pygame.QUIT:
						return 0
	pygame.display.flip()
	clock.tick(200)
t = start(w)
if t == 0:
	running = 0 
	playing = 0
	one = 0
if t == 1:
	l2 = l
	l3 = l1      
	one = 1
  	running = 1
	playing = 1	
if t == 2:
	l2 = lsub
	l3 = l1sub      
	one = 1
  	running = 1
	playing = 1		 	        	
while playing:
	w = Bunny(screen, 50, 50,'bunny1.png')
	al =[]
	next = 1	
	foods = []
	for i in range(10):
		a = random.randint(50, width-100)
		b = random.randint(50, height-100)
		foods.append((a,b))
	score = 0
	p = 10
	if len(l2) > 1:
		n = random.randint(0,(len(l2)-1))
	else:
		n = 0
	while one:
		qq = 1
		if len(l2) == 0 :
			while qq:
				screen.fill((0, 0, 0))
				text = w.write(screen, "TOTAL POINTS", (0,255,0), width, height, 0, 0,80)
				point = str(points)
				text = w.write(screen, point, (0,255,0), width, height, 0, 120,100)
				b = w.create_button(screen, (107,142,35), (width-100), (height-50), 100, 50, "NEW GAME", (255,255,255),20)
				for event in pygame.event.get():
					if event.type == pygame.MOUSEBUTTONDOWN:
						if w.pressed(pygame.mouse.get_pos()):
				 	        	if start(w) == 1:
								f = open('add.txt')
								l = f.readlines()
								f.close()
								f1 = open('answers.txt')
								l1 = f1.readlines()
								f1.close()  
								l2 = l
								l3 = l1    
								print l2,l3
								one = 1
							  	running = 1
								qq = 0
								points = 0
								n = random.randint(0,(len(l2)-1))
							if start(w) == 2:
								f = open('subtraction.txt')
								l = f.readlines()
								f.close()
								f1 = open('answer.txt')
								l1 = f1.readlines()
								f1.close()  
								l2 = l
								l3 = l1    
								print l2,l3
								one = 1
							  	running = 1
								qq = 0
								points = 0
								n = random.randint(0,(len(l2)-1))
					elif event.type == pygame.QUIT:
					 	running = 0 
						playing = 0
						one = 0
						qq = 0
				pygame.display.flip()
				clock.tick(200)
		que = l2[n]
		#que = que.strip('\\n')
		print que
		win = int(l3[n])
		screen.fill((0, 0, 0))
		text = w.write(screen, que, (107,142,35), width, height, 0, 0,100)
		b = w.create_button(screen, (107,142,35), (width-100), (height-50), 100, 50, "Play", (255,255,255),20)
		for event in pygame.event.get():
			if event.type == pygame.MOUSEBUTTONDOWN:
				if w.pressed(pygame.mouse.get_pos()):
		 	               one = 0
				       l2.pop(n)
				       l3.pop(n)
				       running = 1			
		        elif event.type == pygame.QUIT:
			 	running = 0 
				playing = 0
				one = 0
		
		pygame.display.flip()
		clock.tick(100)
	while running:
		screen.fill((0, 0, 0))
		text = w.write(screen, que, (107,142,35), width, height, 0, 0,36)	
		w.background.blit(text, (200,0))
		screen.blit(w.background, (0, 0))
		
		text = w.write(screen, "Carrots:",(107,142,35), width+180,30, 0, 0,30)
		
		for food in foods:
			screen.blit(foodi, food)
		screen.blit(end,(width-50,height-50))
		w.move()
		w.draw()
		point = str(10-len(foods))
		text = w.write(screen, point,(107,142,35), width+280,30, 0, 0,30)
		if  w.x <= 0:
		     	 w.x = width - 10
		if  w.x >= width:
		     	 w.x = 0
		if w.y <= 0 :
			w.y = height - 10
		if w.y >= height-1 : 
			w.y = 0 
		for i in range(p):
			(a,b) = foods[i]
			if w.x + 30 <= a + 32 and w.x + 30 >= a:
				if w.y + 20 <= b + 32 and w.y + 20 >= b:
					score = score+1
					ate = foods.pop(i)
					al.append(ate)
					p = p-1
					pickUpSound.play()
					break
		bn = w.create_button(screen, (107,142,35), (width-50), (0), 50, 50, "Undo", (255,255,255),20)
		for event in pygame.event.get():
		 if event.type == pygame.QUIT:
		 	running = 0 
			playing = 0 
		 elif event.type == pygame.KEYDOWN:
		 	w.key_event(event)
		 if event.type == pygame.MOUSEBUTTONDOWN:
			if w.pressed(pygame.mouse.get_pos()):
				if len(al) > 0:
        	       			undo = al.pop()
					foods.append(undo)
					score = score - 1
					p = p + 1
		if w.x <= width and w.x > (width-50) :
			if w.y <= height and w.y > (height -50):
				if win == score:
					points = points + 10
					while next:
						screen.fill((0, 0, 0))
						text = w.write(screen, "CORRECT!", (0,255,0), width, height, -50, -50,100)
						point = str(points)
						text = w.write(screen, point, (0,255,0), width, height, 0, 120,100)
						b = w.create_button(screen, (107,142,35), (width-100), (height-50), 100, 50, "Next", (255,255,255),20)
						for event in pygame.event.get():
							if event.type == pygame.MOUSEBUTTONDOWN:
								if w.pressed(pygame.mouse.get_pos()):
			 	        	       			next = 0
									running = 0
									one = 1
							elif event.type == pygame.QUIT:
							 	running = 0 
								playing = 0
								one = 0
								next  = 0 
						pygame.display.flip()
						clock.tick(100)
				else:
					while next:
						screen.fill((0, 0, 0))
						point = str(points)
						text = w.write(screen, "WRONG!", (0,255,0), width, height, -50,-50,100)
						text = w.write(screen, point, (0,255,0), width, height, 0, 120,100)
						b = w.create_button(screen, (107,142,35), (width-100), (height-50), 100, 50, "Next", (255,255,255),20)
						for event in pygame.event.get():
							if event.type == pygame.MOUSEBUTTONDOWN:
								if w.pressed(pygame.mouse.get_pos()):
			 	        	       			next = 0
									running = 0
									one = 1
							elif event.type == pygame.QUIT:
							 	running = 0 
								playing = 0
								next  = 0 
								one = 0
						pygame.display.flip()
						clock.tick(100)
		pygame.display.flip()
		clock.tick(100)
	
	pygame.display.flip()
	clock.tick(100)
