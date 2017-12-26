===================================
CKEditor for Django admin
===================================

**CKEditor (WYSIWYG editor) integration app for Django admin**.

http://ckeditor.com/


Documentation
=============

See `Django Suit documentation <http://django-suit.readthedocs.org/en/develop/wysiwyg.html>`_ on WYSIWYG editors.


Build Status
============

Django Suit CKeditor app uses Travis CI to perform tests on different Django and Python versions.

.. |master| image:: https://travis-ci.org/darklow/django-suit-ckeditor.png?branch=master
   :alt: Build Status - master branch
   :target: http://travis-ci.org/darklow/django-suit-ckeditor

|master|

==============================
在原基础上添加了上传插件
=============================
1.config.js 添加了url粘贴代码上传url地址
2.python处理上传代码
def uploader(request):
    image = request.FILES.get("upload")
        image_name = datetime_image_name()
	    white_image = get_static_lujing(image_name)

	        with  open(white_image, "wb") as f:
		        f.write(image.read())

			    tupian = """{"uploaded": 1,"fileName": "%s","url": "/static/images/%s"} """ % (image_name, image_name)

			        return HttpResponse(tupian)


