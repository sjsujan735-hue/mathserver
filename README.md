# Ex.05 Design a Website for Server Side Processing
# Date:27/11/25
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
math.html

<html>
    <head>
        <style>
            body{
                margin-top: 20%;
                font-weight: bold;
            }
        </style>
        <script>
            function power()
            {
                const i=document.getElementById("in").value;
                const r=document.getElementById("resistance").value;
                const p= i*i*r; 
                document.getElementById("answer").innerText="Power :"+ p;
            }
        </script>
    </head>
        <body background="C:\Users\anish\OneDrive\SEC\FWAD\UNIT 3 HTML\bg\4.jpg">
            <center>
                <input type="number" placeholder="Enter Intensity" id="in"><br><br>
                <input type="number" placeholder="Enter Resistance" id="resistance"><br><br>
                <input type="button" onclick="power()" value="Calculate power"><br><br>
                <label id="answer"></label>
            </center>
        </body>
</html>

views.py

from django.shortcuts import render 
def powerofbulb(request): 
    context={} 
    context['power'] = "0" 
    context['i'] = "0" 
    context['r'] = "0" 
    if request.method == 'POST': 
        print("POST method is used")
        i = request.POST.get('intensity','0')
        r = request.POST.get('resistance','0')
        print('request=',request) 
        print('intensity=',i) 
        print('resistance=',r) 
        power = (int(i)**2)*int(r)
        context['power'] = power 
        context['i'] = i
        context['r'] = r 
        print('Power=',power) 
    return render(request,'mathapp/math.html',context)

    urls.py

    from django.contrib import admin 
from django.urls import path 
from mathapp import views 
urlpatterns = [ 
    path('admin/', admin.site.urls), 
    path('powerofbulb/',views.powerofbulb,name="powerofbulb"),
    path('',views.powerofbulb,name="powerofbulbroot")
]
```
# SERVER SIDE PROCESSING:
<img width="1920" height="1200" alt="Screenshot 2024-12-06 215055" src="https://github.com/user-attachments/assets/04c828cc-fe89-44e0-b084-2d2a1d4336e4" />

# HOMEPAGE:
<img width="1920" height="1200" alt="Screenshot 2024-12-06 215005" src="https://github.com/user-attachments/assets/067611c0-1b41-480b-8842-a114752b4527" />


# RESULT:
The program for performing server side processing is completed successfully.
