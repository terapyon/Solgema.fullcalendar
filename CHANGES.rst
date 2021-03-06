
Changelog
=========

2.1.3 (unreleased)
------------------

- Fixed problem with blocked scrollbar after validation error in add/edit 
  form. Remark: the whole edit popup-thingy is very ugly this way. 
  Refactoring needed.
  [thet, jensens]

- Show current month by default instead of next month. In Javascript, the first
  month, January, starts with 0 and December is 11.
  [thet]

- Fix events dict for ATContentType based ATEvent types, so that they are
  displayed again.
  [thet]

- Trigger event after display form was loaded. thus it is possible to rebind
  events for loaded code.
  [jensens]

- Rename IListBaseQueryTopicCriteria to more genric IListBaseQueryCriteria,
  includes BBB. This avoids confusion. Some PEP8fying.
  [jensens]

- Enable ical export for new style collections
  [jensens]

- portal_type works as topic criterion without issue in event sources.
  [seanupton]

- Handle operator-only query strings accordingly.
  [thet]

- Allow selection of initial view by request parameters.
  [rnix]

- Fixed ajax called pages with json content (Diazo compatibility).
  [fmoret]

- Fixed calendar navigation button toggle and add a transition.
  [thomasdesvenain]

- Corrected output of plone.app.event iCalendar export to avoid nesting
  VCALENDAR blocks, rather wrapping 1..* VEVENT blocks inside one VCALENDAR.
  [seanupton]

- Normalize ICS export line endings to match RFC 5545 requirements (consistent
  with what ATCT does, but using a function that could support possibly mixed
  or inconsistent line endings in source text).
  [seanupton]

- Drag-and-drop supports dexterity-based plone.app.event type
  [seanupton]

- plone.app.event Dexterity type compatibilty:
    * Conditional support overlay event display
    * iframe (quick) add form support
    * iframe edit support
    * drag-resize to change duration
    * indexer for full-day events uses IEventAccessor adapter
    * drag-and-drop support for discrete-time and all-day events.
    * Add menu support and event copy/paste compatibility.
    * Use get_uid() to support plone.uuid based UID.

  [seanupton]

- getCopyObjectsUID() identically defined in two view modules, de-duplicated.
  [seanupton]

- View adapters use UID getter (get_uid) indirection from browser.actions,
  supporting either accessor (AT) or property (dexterity) getting of
  start/end values on contexts, casting/normalizing all to DateTime
  (possibly from datetime.datetime for Dexterity-based contexts such as a
  type from plone.app.event). Added conditional adapter registration for
  plone.event.interfaces.IEvent to SolgemaFullcalendarEventDict.
  [seanupton]

- Show object actions links in view popup, provide ability to link to event
  actions in new window/tab target without being forced to use context menu.
  [seanupton]

- Fix form widget name in query string for dexterity-based plone.app.event
  type add form (minute input of each respective datetime field)
  [seanupton]

- Conditional plone.uuid / plone.app.uuid support, with backward compatibility
  fallback.  Use IUUID when available to lookup UID of item.  Added utils.py.
  [seanupton]

- When plone.app.event is both importable and installed as site product,
  display message indicating that browser adjusts events to local time.
  [seanupton]

- SFDisplayAddMenu JSON outputs first portal_type found for a Type name in
  portal_types, will be necessary for plone.app.event+Dexterity support.
  [seanupton]

- Replace search-based target folder selection widget with dependency on
  plone.formwidget.contenttree -- makes browing for a target folder more
  intuitive, also adds package and profile dependency.
  [seanupton]

- Restored compatibility with plone.app.event and recurring events.
  [thet]

- fixed bug when CriteriaItems is False
  [jensens, benniboy]

- workaround for archetypes.querywidget bug see: https://dev.plone.org/ticket/13144
  [jensens, benniboy]

2.1.2 (2012-08-22)
------------------

- Added adapters and view to be compatible with plone.app.collection.
  [fmoret]

- Fixed bug with eventdropping in agenda
  [fmoret]

2.1.1 (2012-06-06)
------------------

- Fixed some bugs in the adapters and actions ("KeyError: Type" when adding event and "ComponentLookupError"
  when workflow transition.)
  [fmoret]

2.1.0 (2012-05-15)
------------------

- Added the fullcalendar_view for Folders. The view displays the events in the folder or use each subfolder as source.
  [fmoret]

- Added the ability to add Google Calendar Sources to the fullcalendar in addition to Plone standard source.
  [fmoret]

- Added Calendar widget to easily change the fullcalendar date.
  [fmoret]

- Restored Plone 3.3.x compatibility
  [fmoret]

- Added DaySplit View which shows the events in seperate columns regarding the selected collection criteria.
  [fmoret]

- Use eventSources instead of events to get Events. Delegate the event's color attribution to fullcalendar.
  [fmoret]

- Fix height of iframe in the popup for adding events in IE.
  [pbauer]

- Created New 2.1.0 version as fullcalendar will no more be compatible with Plone under 4.x
  [fmoret]

2.0.3 (2012-04-12)
------------------

- Fix infinite recursion error in SolgemaFullcalendarEventJS's __init__ method.
  [pbauer]

- Fixed ical export on collection with plone.app.event installed.
  [vincentfretin]

- Prevent that all pages become non-cacheable.
  SolgemaFullcalendarActionGuards wrongly inherited from BaseActionView which
  sets "Pragma: no-cache".
  [weberlar]

- Many fixes on paste event feature.
  [thomasdesvenain]

- Reccurence support uses adapter.
  [thomasdesvenain]

- Added solgemafullcalendar_view for events also. (very useful with
  recurring events with a lot of occurrences)
  [fmoret]

- Add z3c.autoinclude to target plone. No more need to include zcml in buildout
  [toutpt]

- Check also for portal_type in the Topic query (not just 'Type').
  [jcbrand]

- Hide the spinner after closing the add/edit event dialogs.
  [jcbrand]

- Add a zcml browser:menuItem entry to give the dynamic view a human readable title.
  [jcbrand]

- Add collective.js.fullcalendar as dependency in  metadata.xml
  [jcbrand]

- Add Italian translation
  [giacomos]

- Add needed jqueryui plugins explicitly using registry.xml step
  [toutpt]

- Add Nederlands translation
  [cirb]

2.0.2 (2011-11-28)
------------------

- Fixed a bug on SFAllowedRolesAndUsersModify index
  that could make cut/paste actions fail on whole site.
  [thomasdesvenain]

- Fixed ical export.
  [thomasdesvenain]

- Calendar export works with plone.app.event future.
  [thomasdesvenain]

2.0 (2011-10-18)
----------------

- Dependencies: Added collective.js.fullcalendar to product dependencies
  so that it installs automatically.
  [fmoret]

- Fixed: Event adding/editing popupu is now resized on scroll to get the
  correct height.
  [fmoret]

- Added: Extra css class added on events in calendar are now queries by
  adapters.
  [fmoret]

- Fixed: Changed static CSS selectors (for undefined colors) so colors
  get applied correctly.
  [thomasdesvenain]

- UI: a lock icon in displayed on private events.
  [thomasdesvenain]

- ICal export of future events.
  [thomasdesvenain]

- API: If event do not have a 'type-x' class,
  it is not displayed with a SF_x_light view in a popup,
  but a new window is open.
  [thomasdesvenain]

- UI: query criterion labels are clickable.
  [thomasdesvenain]

- Fixed: we needed 'Modify portal content' on calendar
  to change the transition of an event.
  Transition permission on event itself is enough.
  [thomasdesvenain]

- Optimization: Huge optimization on calendar events getting.
  (More than 10 times faster)
  [thomasdesvenain]

- API: Source of events are now adapters that can be customized.
  Provide an IEventSource adapter for a specific layer or context
  to get the list of events to display (or to export under ical).
  Adapter without a name will replace default source event.
  Adapter with a name will add a source event to default one.
  [thomasdesvenain]

- API: Code cleanup to make color management easier to customize.
  - Cleanup component registration so that color filter is easier to customize.
  - Use an adapter to get event brain classes.
  [thomasdesvenain]

- Refactor: remove ``solgemafullcalendar_`` prefix from most module names.
  [thomasdesvenain]

- Refactor: Use collective.js.colorpicker and collective.js.fullcalendar package
  instead of embedding code.
  [thomasdesvenain]

- Fixed: Fixed date formats in french.
  [thomasdesvenain]


1.10 (2011-08-16)
-----------------
- Internationalization: Updated english translation Solgema.fullcalendar.po
  [fmoret]

- Fixed: Changed generated CSS selectors for events on fullcalendar so colors
  get applied correctly.
  [davidjb]

- Fixed: Avoid CSS generation throwing an error if colors haven't been
  specified yet and we have a non-existing colors dict.
  [davidjb]

- Fixed: Allow add menu to display even if the current context (doesn't have
  a query specified yet.
  [davidjb]

- Internationalization: Allow calendar properties form buttons to have a
  default English translation.
  [davidjb]

- Internationalization: Fixing some French messages in the English translation.
  [davidjb]


1.9 (2011-06-16)
----------------

- The ui-lightness skin for jqueryui has been removed. You can add your own
  jqueryui skin if you want to.
  [fmoret]

- Added the possibility to choose short day name format
  (short: 2 characters or abbreviated: 3 characters).
  [fmoret]

- Fixed: week-view didn't translate saturday.
  [pbauer]

- Upgrade to fullcalendar-1.5.1. Remove unused js-files/
  [pbauer]

- Add german translation and german date-formats
  [pbauer]

- Show reccurring events if plone.event is available.
  [vincentfretin]

- Security: use 'Change portal topics' permission
  to manage access to Calendar properties.
  [thomasdesvenain]

- Security: check 'Add portal content' permission on target folder
  instead of 'Modify portal' content on calendar
  to allow adding an event on the calendar.
  [thomasdesvenain]

- Fixed: disallow caching ajax action views,
  to avoid issues behind cache proxies.
  [thomasdesvenain]

- Fixed: event popup is translated.
  [thomasdesvenain]

- Fixed: adding 'all day' event add an event from 00:00 to 23:55.
  [fmoret]

- Fixed: remove duplicated scroll in popup.
  [thomasdesvenain]

- Fixed: closing popups after an event has been added works.
  [fmoret]

- Internationalization: translation files generation with i18ndude.
  [thomasdesvenain]

- Internationalization: fixed event popup translation.
  [thomasdesvenain]

- Internationalization: calendar parameters tab
  and calendar display layout are internationalized and french translated.
  [thomasdesvenain]

- Infrastructure : timezones forward compatibility.
  [vincentfretin, thomasdesvenain]

- Infrastructure : plone.app.event forward compatibility :
  event view uses event_view macros by default,
  never use direct access to startDate and endDate attributes for timezones compatibility.
  [vincentfretin]

- Infrastucture: use Generic setup to install some dependencies.
  [thomasdesvenain]

- Infrastucture: hide upgrade profiles on Plone site creation form.
  Upgrade profiles don't appear in root profiles.
  [thomasdesvenain]

- Pep8 & pyflakes.
  [thomasdesvenain]

- Plone 4.1 compatibility.
  [thomasdesvenain]

- Imported Solgema.fullcalendar in collective.
  [fmoret, thomasdesvenain]


1.8
---

- Clicking on an event always asks for SFLight_event_view.pt. Allows the use of xdv theming
  (thanks to Sylvain Boureliou)

- Comes with ui lightness 1.8.9 theme

1.7
---

- Removed own jqueryui and added collective.js.jqueryui (Thanks to Thomas Desvenain)

- Fixed views and javascript files (fix issue #17 and #20, Thanks to Christian Lederman!)

- Fixed dependencies declarations (Thanks to Olav Peeters)

- Added a small workaround to solve a conflict between base jqueryui css and custom jqueryui lightness css.

- Based on fullcalendar 1.4.10 (Thanks to Adam Arshaw)

1.6
---

- Fixed wrong call to getUrl method and completed with here/absolute_url

- Fixed bad condition expression in actions (Thanks to Thomas Desvanain)

- Added some steps to be sure (as sure as possible) that solgemafullcalendar_view remains in topic views

1.5
---

- Fixed adapting content that is not attribute annotable.
  (changed indexer in catalog.py ) that fixes bug with plone.app.discussion.

- Fixed cancel button and dialog close when editing. The edited event remained locked when closing dialog.

- Fixed content type for solgemafullcalendar_vars.js


1.4
---

- Now based on Fullcalendar v 1.4.8

- Fixed IE7 bug (thanks to Kyle Homstead)

- Added the subtopics display in solgemafullcalendar_view (thanks to Christian Ledermann)

- Added a <noscript> tag in solgemafullcalendar_view so that events are display even if javascript is not enabled.
  This can be disabled in Calendar View settings. (thanks to Christian Ledermann)

1.3
---

- Added the ability to choose your own color for events in the calendar. The color is linked to the topic's critrias.

- Added colorpicker widget to choose the colors in Calendar View settings

- Fixed Content Menu showing under calendar events


1.2
---

- Fixed calendar Height Setting

- Using now jquery ui 1.8.5 (added javascripts for 1.8.5 and removed 1.8.4)

1.1
---

- Created an adapter to filter for editable events so that it can be easily overriden.

- Solgema.ContextualContentMenu package included in configure.zcml

- Installs Solgema.ContextualContentMenu properly

- Fix jquery.js to 1.4.2 version (jquery.js added in skins directory)

- Fix height dialog box

- Added an override review_state in topic query for Admins so that the can see private events in calendar
  Event if they are not searched basically by the topic (e.g. for default events aggregator)


1.0
---

- Added relative start hour and relative start day

- Fixed paste action in contextual content menu (when nothing in clipboard)

- Fixed error when deleting topic's criterion after having set them in calendar view criterias.

- Several bug fixed


0.3
---

- Added automatic dependencies installation in install.py ( installation of Solgema.ContextualContentMenu )

- Changed the javascript in SFAjax_base_edit.cpt so that when editing through calendar,
  the dialog's iframe is resized to display the entire edit form ( fixes issue #1 )

- Changed Dialog title when adding content
  (msgid was "label_add_type" in Plone 3 and now 'heading_add_item' in Plone 4).


0.2
---

- Added a topicRelativeUrl variable into solgemafullcalendar_vars to fix the cookies path.
  (fix an issue with mutiple cookies when the topic is default view of a folder)
