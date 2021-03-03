# django-signed-media
Permission based access to media, similar to AWS S3's media signatures.

Seems like it's already been accomplished! Links:

- https://medium.com/@ekeydar/signed-urls-storage-for-django-58feecbd94a8
- https://stackoverflow.com/questions/56628595/how-to-configure-django-to-generate-signed-urls-for-media-files-with-google-clou
- https://github.com/cobusc/django-protected-media Not sure about this... login is required? No signing? Eh.

A huge deterrent for me is people uploading to my server
could easily crash the server... I would need a separate machine,
a separate nginx file to configure max file size (different from
actual website which should just be bear minimum i.e. like 5 mb at most
of POST data).

That would mean presigned posts just like S3 if I were to do it on
a separate server. Because I want my main website to be fast,
but if I'm having to wait for people uploading bunch of files
at once, then the entire website slows down.

I suppose that shouldn't be too hard. We can take that signature method from the first
link (the medium article) and that would act as "verifying the post." But decrypting it...
EHHHH

Ok so I guess I'm actually making this a package since it isn't one yet.
