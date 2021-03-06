.. highlight:: none
.. _dev-documentation:

Contributing documentation
==========================

For documentation, we encourage contributions to Zotonic from the
community even more!


We use git for documentation. For large documentation changed, you
should take the same approach as with :doc:`contributing`: e.g. create
a fork of Zotonic, create a topic branch, make the changes, push, pull
request.

However, for small changes, typo's, et cetera, Github provides a nice
edit button which you can use to edit these ``.rst`` files.


Writing documentation
---------------------

Emacs' `rst-mode
<http://docutils.sourceforge.net/docs/user/emacs.html>`_ does the job
for most things. It has nice coloring and indenting. Paragraphs are
hard-wrapped at 80 characters with single newlines.


Heading styles
..............

Use the following convention for headings::

  First-level heading
  ===================

  Second-level heading
  --------------------

  Third-level heading
  ...................


When writing documentation of modules, actions, etc; anything under
``ref/``; the first level heading is already there for you, generated
in the ``meta-*.rst`` file. So you should only use ``----------`` and
``..........`` for the headings in the ``ref/`` files.


When using Emacs, this little snippet helps with adding underlines to headings::

   (defun underline-with-char (char)
     (interactive (list (read-from-minibuffer "Char: ")))
     (when (= 0 (length char))
       (error "Need a character"))
     (setq char (aref char 0))             ; Ignore everything but the first char.
     (save-excursion
       (goto-char (point-at-eol))
       (insert "\n"
               (make-string (- (point-at-eol)
                               (point-at-bol))
                            char))))

From a mailing list `post <http://lists.gnu.org/archive/html/help-gnu-emacs/2008-05/msg00305.html>`_.


References
..........

Be generous with using references (``:ref:`pagelabel```) in your
writing. The more terms are linked to their respective documentation
pages, the better. Only make the first occurrence of a term a
reference to its page, though; consequent occurrences can be made
```italic```.

Add a ``.. seealso::`` section at the bottom to highlight any other
pages which are closely related to the current one, for example::

  .. seealso:: :ref:`dev-contributing`


Table styles
............

For the easy editing of tables, we use Emacs' `table-mode
<http://emacswiki.org/emacs/TableMode>`_, which at first has a bit of
a learning curve but actually works pretty well when creating the
ascii-art tables that the RST format requires you to use.

In general, we use this style of tables::

  +--------------------+-------------------+
  | Header             |Other header       |
  +====================+===================+
  |This is the table   |Some more contents |
  |cell contents       |                   |
  +--------------------+-------------------+

.. seealso:: :ref:`dev-contributing`

   
