[JavaScript] onMouseEnter and onMouseLeave Suppport for Old Browsers
####################################################################

:date: 2012-10-02 00:07
:modified: 2015-02-26 19:48
:tags: html, JavaScript, mouseenter, mouseleave
:category: JavaScript
:summary: JavaScript Cross-Browser Implementation of onMouseEnter and onMouseLeave Event
:og_image: http://www.javatpoint.com/images/javascript/javascript_logo.png
:adsu: yes


onmouseenter_ and onmouseleave_ event are not supported in old browsers. If you
need mouseenter_ or mouseleave_ event and want to support old browsers at the
same time, this post shows how to do it.

.. rubric:: `Demo <{filename}/code/javascript-mouseenter-mouseleave/mouseenterleave.html>`_
      :class: align-center

Implementation of MouseEnter and MouseLeave
+++++++++++++++++++++++++++++++++++++++++++

.. show_github_file:: siongui userpages content/code/javascript-mouseenter-mouseleave/mouseenter-mouseleave.js
.. adsu:: 2

Usage
+++++

Put the above code snippet in your JavaScript.

Register onmouseenter_ event handler *sampleHandler* to element *sampleElement*
by:

.. code-block:: javascript

  addMouseEnterEventListener(sampleElement, sampleHandler);

Register onmouseleave_ event handler *sampleHandler* to element *sampleElement*
by:

.. code-block:: javascript

  addMouseLeaveEventListener(sampleElement, sampleHandler);

.. adsu:: 3

----

Reference:

.. [1] `[JavaScript] Comparison of MouseEnter MouseLeave MouseOver MouseOut <{filename}../../08/07/javascript-compare-mouseenter-mouseleave-mouseover-mouseout%en.rst>`_


.. _onmouseenter: http://www.w3schools.com/jsref/event_onmouseenter.asp

.. _onmouseleave: http://www.w3schools.com/jsref/event_onmouseleave.asp

.. _mouseenter: https://developer.mozilla.org/en-US/docs/Web/Events/mouseenter

.. _mouseleave: https://developer.mozilla.org/en-US/docs/Web/Events/mouseleave
