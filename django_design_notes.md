## Django notes

* In the begining have a plan

* When you begin to design models try to try to focus on the 	important bits. The information that you need to start the development.

* Drawing a UML at the begining specially for data base helps very much can do this with [StartUML](http://staruml.io/)

* Some times it is better to draw a wireframe from the application or site it helps to gain deeper understanding of the entities involved in the application. to draw your wireframes you can use the [draw.io](https://draw.io/) service, it’s free.

* Model note: when we want to set the current date and time in  a model field we can use the `auto_now_add=True` as argument of the field.

* Model note: The `related_name` parameter will be used to create a reverse relationship where the Board instances will have access a list of Topic instances that belong to it.

	* Django automatically creates this reverse relationship – the related_name is optional. But if we don’t set a name for it, Django will generate it with the name: (class_name)_set. For example, in the Board model, the Topic instances would be available under the topic_set property. Instead, we simply renamed it to topics, to make it feel more natural.


	* In the  Post model, the updated_by field sets the `related_name='+'`. This instructs Django that we don’t need this reverse relationship, so it will ignore it.

* For using bootstrap just one file needed and that is 'bootstrap.min.css' of course for typical uses.

* Raise a 404 page when page not exist this is done by exception handling. also this is a shortcut in django using `get_object_or_404` (part3)

* Form in the right way in part3.

* Don't forget urlpatterns in part3.

* ORM and working with data base in part4.

* ‍‍‍‍‍‍‍`annotate` in part4.