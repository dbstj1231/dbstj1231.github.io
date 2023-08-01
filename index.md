---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "2023 한국어 평가 말하기, 쓰기 자동채점 연구 워크숍"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "양평 블룸비스타 호텔"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "ko"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "ko"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: "37"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "127"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "2023.08.04(금)-05(토)"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "13:00 - 18:00"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: 2023-08-04      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2023-08-05        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: [] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: []     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: []    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:  # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}


<h2 id="general">Invitation</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% if site.pilot %}
This is a pilot workshop, testing out a lesson that is still under development. The lesson authors would appreciate any feedback you can give them about the lesson content and suggestions for how it could be further improved.
{% endif %}




{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="일시">
  <strong>일시:</strong>
  {{page.humandate}}
</p>
{% endif %}




{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://www.latlong.net/ to find the lat/long of an
address.
{% endcomment %}
{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
{% if page.latitude and page.longitude and online == "false" %}
<p id="장소">
  <strong>장소:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% elsif online == "true_public" %}
<p id="장소">
  <strong>장소:</strong>
  online at <a href="{{page.address}}">{{page.address}}</a>.
  If you need a password or other information to access the training,
  the instructor will pass it on to you before the workshop.
</p>
{% elsif online == "true_private" %}
<p id="장소">
  <strong>장소:</strong> This training will take place online.
  The instructors will provide you with the information you will need to connect to this meeting.
</p>
{% endif %}





{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="참여기관">
  <strong>참여기관:</strong>
  세종학당, 광주교육대학교, 인하대학교, 서강대학교
</p>

<hr/>












{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

https://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.

Note we also have a CodiMD (the open-source version of HackMD)
available at https://codimd.carpentries.org
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{ page.collaborative_notes }}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}













{% comment %}
SCHEDULE

Show the workshop's schedule.

Small changes to the schedule can be made by modifying the
`schedule.html` found in the `_includes` folder for your
workshop type (`swc`, `lc`, or `dc`). Edit the items and
times in the table to match your plans. You may also want to
change 'Day 1' and 'Day 2' to be actual dates or days of the
week.

For larger changes, a blank template for a 4-day workshop
(useful for online teaching for instance) can be found in
`_includes/custom-schedule.html`. Add the times, and what
you will be teaching to this file. You may also want to add
rows to the table if you wish to break down the schedule
further. To use this custom schedule here, replace the block
of code below the Schedule `<h2>` header below with
`{% include custom-schedule.html %}`.
{% endcomment %}

<h2 id="schedule">Schedule</h2>

{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% elsif site.carpentry == "incubator" %}
This workshop is teaching a lesson in [The Carpentries Incubator](https://carpentries-incubator.org/).
Please check [the lesson homepage]({{ site.incubator_lesson_site }}) for a list of lesson sections and estimated timings.
{% endif %}

{% comment %}
Edit/replace the text above if you want to include a schedule table.
See the contents of the _includes/custom-schedule.html file for an example of
how one of these schedule tables is constructed.
{% endcomment %}

{% if site.pilot %}
The lesson taught in this workshop is being piloted and a precise schedule is yet to be established. The workshop will include regular breaks. Please [contact the workshop organisers](#contact) if you would like more information about the planned schedule.
{% endif %}

<hr/>













{% comment %}
CONTACT
{% endcomment %}
<h2 id="contact">Contact</h2>
<p>서강대학교 청각지능연구실<br>(speech.sogang.ac.kr)</p>
<p>문의처: 정윤서( 이메일: dbstj1231@sogang.ac.kr | 전화 010-5478-9310 )</p>

<hr/>
