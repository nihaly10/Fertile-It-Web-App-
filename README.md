# Fertile-It-Web-App-

// models for django 
rom django.db import models


class Product(models.Model):
    Name = models.CharField(max_length=255)
    Price = models.FloatField()
    Stock = models.IntegerField()
    Image_url = models.CharField(max_length=2083)
    
    
// indexes used in html 
{% extends 'basehtml' %}

{% block content %}
    <h1>Products</h1>
    <div class="row">
    {% for product in products %}
        <div class="col">

            <div class="card" style="width: 18rem;">
              <img class="card-img-top" src= "{{ product.Image_url }}" alt="Card image cap">
                <div class="card-body">
                  <h5 class="card-title">{{ product.Name }}</h5>
                  <p class="card-text">Rs.{{ product.Price }} for 50kg</p>
                  <a href="#" class="btn btn-primary">{{ product.Stock }} available</a>
                </div>
            </div>
        
        </div>
   {% endfor %}
    </div>
{% endblock %}
