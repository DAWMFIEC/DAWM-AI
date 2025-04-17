Título
======

.. epigraph::

   No matter where you go, there you are.

   -- Buckaroo Banzai

Hyperlinks
----------

It is a website, so it'll have hyperlinks like http://www.python.org (inline),
or Python_ (external reference), example_ (internal reference),
`Python web site <http://www.python.org>`__ (external hyperlinks with embedded
URI), footnote references (manually numbered [1]_, anonymous auto-numbered [#]_,
labeled auto-numbered [#label]_, or symbolic [*]_), citation references ([12]_),
substitution references (|example|), and _`inline hyperlink targets`
(see Targets_ below for a reference back to here).

reStructuredText has character-level inline markup too. It's ugly to write, but
someone might be using it, so here's an example: **re**\ ``Structured``\ *Text*.

It is also possible to link to documented items, such as
:class:`api_sample.RandomNumberGenerator`.

Code with Sidebar
-----------------

.. sidebar:: A code example

    With a sidebar on the right.

.. code-block:: python
   :caption: Code blocks can also have captions.
   :linenos:

   print("one")
   print("two")
   print("three")
   print("four")
   print("five")
   print("six")
   print("seven")
   print("eight")
   print("nine")
   print("ten")
   print("eleven")
   print("twelve")
   print("thirteen")
   print("fourteen")


.. admonition:: arg1
   :class: arg1
   :name: arg1

   abcdefghijklmnopqrstuvwxyz

References
==========

Footnotes
---------

.. [1] A footnote contains body elements, consistently indented by at
   least 3 spaces.

   This is the footnote's second paragraph.

.. [#label] Footnotes may be numbered, either manually (as in [1]_) or
   automatically using a "#"-prefixed label.  This footnote has a
   label so it can be referred to from multiple places, both as a
   footnote reference ([#label]_) and as a hyperlink reference
   (label_).

.. [#] This footnote is numbered automatically and anonymously using a
   label of "#" only.

.. [*] Footnotes may also use symbols, specified with a "*" label.
   Here's a reference to the next footnote: [*]_.

.. [*] This footnote shows the next symbol in the sequence.

Citations
---------

.. [12] This citation has some ``code blocks`` in it, maybe some **bold** and
       *italics* too. Heck, lets put a link to a meta citation [13]_ too.

.. [13] This citation will have one backlink.

Here's a reference to the above, [12]_ citation.

Here is another type of citation: `citation`