# Mini Challenge 2

 

## Create your new posts app

 

### Pre-requisites

Add the following model to your `posts/models.py` file:

 

```

from django.contrib.auth import get_user_model

...

 

class Post(models.Model):

    title = models.CharField(max_length=128)

    subtitle = models.CharField(max_length=256)

    author = models.ForeignKey(

        get_user_model(),

        on_delete=models.CASCADE

    )

    body = models.TextField()

    created_on = models.DateTimeField(auto_now_add=True)

 

    def __str__(self):

        return self.title

 

    def get_absolute_url(self):

        return reverse("detail", args=[self.id])

```

### Acceptance Criteria

1. Make sure you have the model above and...

1.1. Create a new migration.

1.2. Run all migrations (including the one created in the previous step).

2. Extend the following view classes in `posts/views.py`:

2.1. ListView

2.2. DetailView

2.3. CreateView

3. Create all necessary urlpatterns, templates and views to make sure your posts model can be interacted with through your app.

4. Test (run your server and confirm your app works as expected).