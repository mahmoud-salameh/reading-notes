# Intro to Django

## Object-relational mapper

Deﬁne your data models entirely in Python. You get a rich, dynamic database-access API for free — but you can still write SQL if needed.

    class Band(models.Model):
        """A model of a rock band."""
        name = models.CharField(max_length=200)
        can_rock = models.BooleanField(default=True)


    class Member(models.Model):
        """A model of a rock band member."""
        name = models.CharField("Member's name", max_length=200)
        instrument = models.CharField(choices=(
                ('g', "Guitar"),
                ('b', "Bass"),
                ('d', "Drums"),
            ),
            max_length=1
        )
        band = models.ForeignKey("Band")

## URLs and views

A clean, elegant URL scheme is an important detail in a high-quality web application. Django encourages beautiful URL design and doesn’t put any cruft in URLs, like .php or .asp.


To design URLs for an application, you create a Python module called a URLconf. Like a table of contents for your app, it contains a simple mapping between URL patterns and your views.

    from django.urls import path

    from . import views

    urlpatterns = [
        path('bands/', views.band_listing, name='band-list'),
        path('bands/<int:band_id>/', views.band_detail, name='band-detail'),
        path('bands/search/', views.band_search, name='band-search'),
    ]


    from django.shortcuts import render

    def band_listing(request):
        """A view of all bands."""
        bands = models.Band.objects.all()
        return render(request, 'bands/band_listing.html', {'bands': bands})

## Templates

Django’s template language is designed to strike a balance between power and ease. It’s designed to feel comfortable and easy-to-learn to those used to working with HTML, like designers and front-end developers. But it is also flexible and highly extensible, allowing developers to augment the template language as needed.


    <html>
    <head>
        <title>Band Listing</title>
    </head>
    <body>
        <h1>All Bands</h1>
        <ul>
        {% for band in bands %}
        <li>
            <h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>
            {% if band.can_rock %}<p>This band can rock!</p>{% endif %}
        </li>
        {% endfor %}
        </ul>
    </body>
    </html>


Django comes with a full-featured and secure authentication system. It handles user accounts, groups, permissions and cookie-based user sessions. This lets you easily build sites that allow users to create accounts and safely log in/out.

    from django.contrib.auth.decorators import login_required
    from django.shortcuts import render

    @login_required
    def my_protected_view(request):
        """A view that can only be accessed by logged-in users"""
        return render(request, 'protected.html', {'current_user': request.user})


Django offers full support for translating text into different languages, plus locale-specific formatting of dates, times, numbers, and time zones. It lets developers and template authors specify which parts of their apps should be translated or formatted for local languages and cultures, and it uses these hooks to localize web applications for particular users according to their preferences.


    from django.shortcuts import render
    from django.utils.translation import gettext

    def homepage(request):
        """
        Shows the homepage with a welcome message that is translated in the
        user's language.
        """
        message = gettext('Welcome to our site!')
        return render(request, 'homepage.html', {'message': message})

    {% load i18n %}
    <html>
    <head>
        <title>{% trans 'Homepage - Hall of Fame' %}</title>
    </head>
    <body>
        {# Translated in the view: #}
        <h1>{{ message }}</h1>
        <p>
        {% blocktrans count member_count=bands.count %}
        Here is the only band in the hall of fame:
        {% plural %}
        Here are all the {{ member_count }} bands in the hall of fame:
        {% endblocktrans %}
        </p>
        <ul>
        {% for band in bands %}
        <li>
            <h2><a href="{{ band.get_absolute_url }}">{{ band.name }}</a></h2>
            {% if band.can_rock %}<p>{% trans 'This band can rock!' %}</p>{% endif %}
        </li>
        {% endfor %}
        </ul>
    </body>
    </html>


## How Django Works Behind the Scenes

Django is a Python-based web framework used by millions of developers and billions of consumers through popular apps like Instagram. It is open source, meaning the code is available for free on Github and can be downloaded onto any developer’s computer and used alongside the official documentation. However, I find that even professional Django developers have little insight into “how” Django is actually run, both technically and legally/financially, so this post is my attempt to provide a concise overview of it all.

Django was originally developed at the Lawrence Journal-World newspaper by Adrian Holovaty, Simon Willison, and Jacob Kaplan-Moss. The code was open-sourced in 2005 and developers immediately started making contributions to the codebase. Fourteen years later, Django remains under active development, with new major releases every nine months, minor security releases almost monthly, an official issue tracker, and robust discussion on the django-developers Google group.


It turns out that while writing code is fun and developers are generally willing to contribute their time for free to do so, there are a host of decidedly less fun tasks needed to maintain and sustain an open source project. This includes handling any legal/trademark issues, triaging tickets, guiding community discussions, organizing conferences, managing releases, and so on. As a result, almost all popular open source packages have some degree of funding involved, typically in one of three forms:

1. Corporate Sponsor - A group of engineers within a larger, for-profit company decide to open-source internal code. This is how React (Facebook) and Angular (Google) emerged. Typically engineers at the company are paid, in part, to work on open source though community involvement from developers outside of the core company occurs as well. While this structure has the stability of a wealthy benefactor, there can be confusion around the licensing aspects at times.

2. Solo - An individual developer initially creates code, open sources it, and retains default control. This is the case for VueJS, Tailwind CSS, and Laravel, among others. Typically the lead developer either raises contributions directly like Evan You of VueJS, offer add-on services like Spark for Laravel, or the founders provide highly-paid consulting services.

3.  Non-profit - This was Django’s approach early on, in 2008, when the Django Software Foundation was formed to promote, support, and advance Django.

### Django Software Foundation

The DSF supports and maintains Django in a number of capacities. The largest expense, by far, is the Fellows Program, paid contractors who triage tickets, manage releases, and generally perform the unsexy but necessary work needed to keep Django on track.

Tim Graham was the inaugural fellow during its 3-month pilot in the fall of 2014 and became a full-time fellow in 2015. He remained in this role until 2018 before transitioning to a part-time role. Carlton Gibson joined as a part-time Fellow in 2018 and in 2019 Mariusz Felisiak took over from Tim Graham.


### Conclusion


So where does this Django behind the scenes tour leave us? Django’s code is open source and available to all. Django’s organization is managed by a non-profit, the DSF, with a miniscule budget. And Django code is lead by a core team of volunteers, two paid Django Fellows, and a larger group of contributors.