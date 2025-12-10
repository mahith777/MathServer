# Ex.04 Design a Website for Server Side Processing
## Date:

## AIM:10-12-2025
To create a web page to calculate vehicle mileage and fuel efficiency using server-side scripts.

## FORMULA:
M = D / F
<br> M --> Mileage (in km/l)
<br> D --> Distance Travelled (in km)
<br> F --> Fuel Consumed (in l)

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM:
```
urls.py
from django.urls import path
from mathapp import views

urlpatterns = [
    path('', views.fmiles, name='fmiles'),
]
```
```
views.py
from django.shortcuts import render
def fmiles(request):
    km = int(request.POST.get('distance', 0))
    l = int(request.POST.get('liters', 0))
    miles = km / l if request.method == 'POST' and l != 0 else 0
    print("kilometers =", km)
    print("liters =", l)
    print("Mileage =", miles)
    return render(request, 'mathapp/math.html', {'km': km, 'l': l, 'miles': miles})
```
```
math.py
<html>
<head>
    <title>Mileage Calculator</title>
    <style>
        body 
        {
            background: linear-gradient(rgb(174, 8, 8), rgb(74, 232, 108));
        }
        .id1 
        {
            text-align: center;
            color: black;
        }
        .box 
        {
            text-align: center;
            width: 50%;
            background-color: rgb(247, 152, 215);
            border: solid 4px rgb(213, 203, 247);
            padding: 20px;
            margin: 50px auto;
        }
        .result 
        {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1 class="id1"><u>Calculate Mileage Here</u></h1>
    <div class="box">
        <h2><u>Mileage Calculator</u></h2>
        <h3>MAHITH M (25001152)</h3>

        <form method="post">
            {% csrf_token %}
            <label>Distance Travelled</label>
            <br>
            <input type="number" name="distance"> km
            <br>
            <br>
            <label>Liters Consumed</label>
            <br>
            <input type="number" name="liters"> L
            <br>
            <br>
            <button type="submit">Calculate</button>
            <br>
            <br>
            <label>Mileage</label>
            <br>
            <input class='result' type="number" name="Mileage" value={{miles}}x>Km/L
        </form>
    </div>
</body>
</html>


```


## OUTPUT - SERVER SIDE:
![alt text](<Screenshot (40).png>)

## OUTPUT - WEBPAGE:

![alt text](<Screenshot (39).png>)
## RESULT:
The a web page to calculate vehicle mileage and fuel efficiency using server-side scripts is created successfully.
