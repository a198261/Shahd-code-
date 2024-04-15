import math
import turtle

# تهيئة النافذة والمظهر
turtle.shape("turtle")
turtle.setup(width=900, height=700)
turtle.speed(0)
turtle.bgcolor('black')
turtle.color('red')

# تعريف الدوال لرسم القلوب
def heart1(h):
    return 15 * math.sin(h) ** 3

def heart2(h):
    return 12 * math.cos(h) - 5 * math.cos(2 * h) - 2 * math.cos(3 * h) - math.cos(4 * h)

# رسم القلب الكبير
turtle.penup()
turtle.goto(heart1(0) * 20, heart2(0) * 20)
turtle.pendown()

for i in range(400):
    x, y = heart1(i) * 20, heart2(i) * 20
    turtle.goto(x, y)

# كتابة الاسم
turtle.penup()
turtle.goto(0, 35)
turtle.pendown()
turtle.color('green')  # تحديد لون الكتابة
turtle.write("Shahd", align='center', font=('Arial', 30, 'normal'))

# رسم القلب الصغير داخل القلب الكبير
turtle.penup()
turtle.goto(heart1(0) * 20, heart2(0) * 20 - 100)
turtle.pendown()

turtle.color('red')  # تحديد لون القلب
for i in range(300):
    x, y = heart1(i) * 10, heart2(i) * 10 - 100
    turtle.goto(x, y)

# رسم القلب الأصغر داخل القلب الصغير
turtle.penup()
turtle.goto(heart1(0) * 20, heart2(0) * 20 - 150)
turtle.pendown()

for i in range(200):
    x, y = heart1(i) * 5, heart2(i) * 5 - 150
    turtle.goto(x, y)

# رسم القلب الأصغر داخل القلب الأصغر
turtle.penup()
turtle.goto(heart1(0) * 20, heart2(0) * 20 - 180)
turtle.pendown()

for i in range(150):
    x, y = heart1(i) * 2, heart2(i) * 2 - 180
    turtle.goto(x, y)

# كتابة "أحبك"
turtle.penup()
turtle.goto(0, -180)
turtle.pendown()
turtle.color('green')  # تحديد لون الكتابة
turtle.write("I Love You", align='center', font=('Arial', 40, 'normal'))

# انهاء البرنامج
turtle.done()
