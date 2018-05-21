# oneone
import turtle as tp


h = 10

def draw_node_a(n):
    #3
    #1
    if n>0:
        draw_node_b(n-1)
        draw(0,h)
        draw_node_a(n-1)
        draw(h,0)
        draw_node_a(n-1)
        draw(0,-h)
        draw_node_c(n-1)#


def draw_node_b(n):
    #4
    #2
    #1
    if n>0:
        draw_node_a(n-1)
        draw(h,0)
        draw_node_b(n-1)
        draw(0,h)
        draw_node_b(n-1)
        draw(-h,0)
        draw_node_d(n-1)


def draw_node_c(n):
    #2
    if n>0:
        draw_node_d(n-1)
        draw(-h,0)
        draw_node_c(n-1)
        draw(0,-h)
        draw_node_c(n-1)
        draw(h,0)
        draw_node_a(n-1)

def draw_node_d(n):
    #1
    if n>0:
        draw_node_c(n-1)
        draw(0,-h)
        draw_node_d(n-1)
        draw(-h,0)
        draw_node_d(n-1)
        draw(0,h)
        draw_node_b(n-1)


def draw(dx,dy):
    global x,y
    x = x + dx
    y = y + dy
    tp.goto(x,y)

def initturtle(n):
    tp.penup()
    tp.goto(x,y)
    tp.pendown()
    draw_node_b(n)

x,y = -350,-300

tp.speed(3)
tp.pensize(3)
tp.color("blue")
initturtle(6)
tp.done()
