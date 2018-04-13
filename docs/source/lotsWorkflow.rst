.. _lots_workflow:

Lots Workflow
==============

.. graphviz::

    digraph G {

            subgraph cluster_1 {
                    node [style=filled, fillcolor=seashell2];
                    edge[style=dashed,  arrowhead="vee"];
                    "draft" -> "pending" [color="0.0000 0.0000 0.3882"];
                    edge[style=dashed,  arrowhead="vee"];
                    "pending" -> "verification" [color="0.0000 0.0000 0.3882"];
                    edge[style=solid,  arrowhead="vee"];
                    "verification" -> "pending" [color="0.6667 1.0000 0.5020"];
                    "verification" -> "active.salable" [color="0.6667 1.0000 0.5020"];
                    edge[dir="both"];
                    "active.salable" -> "active.awaiting" [color="0.6667 1.0000 0.5020"];
                    edge[dir="forward"];
                    "active.awaiting" -> "active.auction" [color="0.6667 1.0000 0.5020"];
                    edge[dir="forward"];
                    "active.auction" -> "pending.sold" [color="0.6667 1.0000 0.5020"];
                    edge[dir="forward"];
                    "pending.sold" -> "sold" [color="0.6667 1.0000 0.5020"];
                    color=white;
            }






Legend
--------

   * dashed line - user action
    
   * solid line - action is done automatically
