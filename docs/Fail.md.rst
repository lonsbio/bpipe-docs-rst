The succeed statement
=====================

Synopsis
~~~~~~~~

.. raw:: html

   <pre>
       fail <message>
       fail [text {<text>} | html { <html> } | report(<template>)] to <notification channel name>
   fail [{<text>} | html { <html> } | report(<template>)](text) to channel:<channel name>, 
                                                                  subject:<subject>, 
                                                                  file: <file to attach> 
   </pre>

Availability
~~~~~~~~~~~~

0.9.8.6\_beta\_2 +

Behavior
~~~~~~~~

Causes the current branch of the pipeline to terminate explicitly with a
failure status and a provided message.

In the most simple form, a short message is provided as a string. The
longer forms allow a notification or report to be generated as a result
of the success.

While using ``fail`` as a stand alone construct is possible, the primary
use case is to embed it inside the otherwise clause of a
[[Check\|check]] command, which ensures that Bpipe remembers the status
and output of the check performed.

*Note*: see the [[Send\|send]] command for more information and examples
about the variants of this command that send notifications and reports.

Examples
~~~~~~~~

**Cause an Explicit Failure of the Pipeline**

.. code:: groovy


       fail "Sample $branch.name has no variants - processing cannot continue"

