Resizes image origin to specified size. Compatible with sorl-thumbnail.

Features
========

- Support for Django 1.3, 1.4, 1.5, 1.6 and 1.7
- Python 3 support

Installation
============

    pip install django-resized


Configuration (optional)
========================

settings.py ::

    DJANGORESIZED_DEFAULT_SIZE = [1920, 1080]
    DJANGORESIZED_DEFAULT_QUALITY = 75
    DJANGORESIZED_DEFAULT_KEEP_META = True

Usage
=====

models.py ::

    from django_resized import ResizedImageField

    class MyModel(models.Model):
        ...
        image1 = ResizedImageField(size=[500, 300], upload_to='whatever')
        image2 = ResizedImageField(size=[100, 100], crop=['top', 'left'], upload_to='whatever')
        image3 = ResizedImageField(size=[100, 100], crop=['middle', 'center'], upload_to='whatever')
        image4 = ResizedImageField(size=[500, 300], quality=75, upload_to='whatever')

Options
-------


- **size** - max width and height, for example [640, 480]
- **crop** - resize and crop. ['top', 'left'] - top left corner, ['middle', 'center'] is center cropping, ['bottom', 'right'] - crop right bottom corner.
- **quality** - quality of resized image 1..100
- **keep_meta** - keep EXIF and other meta data, default True


How to run tests
================

    tox
