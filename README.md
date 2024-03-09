# Django_projects
This repository contains key points to Django projects
When creating django models to hold filefield.

in Settings.py add 



MEDIA_ROOT=BASE_DIR/"media"
MEDIA_URL="/media/"



int urls.py in the django project,add



if settings.DEBUG:
    urlpatterns+=static(settings.MEDIA_URL,document_root=settings.MEDIA_ROOT)



ind views.py,this is where to pass the model to the html document.
exmaple



def index(request):
    **Feature1 = Feature.objects.all()**
    return render(request,'index.html',**{'Feature1':Feature1}**)



To display the videos on the html document with the above model,use


  {% for task in Feature1 %} 
    <p>{{task.username}}</p>
    <p>{{task.details}}</p>
    <video width="300px" controls src="{{task.videos.url}}"></video>
    {% endfor %}

    
