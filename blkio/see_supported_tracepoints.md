If you have `perf` installed, you can see the tracepoints in the currently-running kernel via

```
sudo perf list 'block:*'

List of pre-defined events (to be used in -e):

  block:block_bio_backmerge                          [Tracepoint eve>
  block:block_bio_bounce                             [Tracepoint eve>
  block:block_bio_complete                           [Tracepoint eve>
  block:block_bio_frontmerge                         [Tracepoint eve>
  block:block_bio_queue                              [Tracepoint eve>
  block:block_bio_remap                              [Tracepoint eve>
  block:block_dirty_buffer                           [Tracepoint eve>
  block:block_getrq                                  [Tracepoint eve>
  block:block_plug                                   [Tracepoint eve>
  block:block_rq_complete                            [Tracepoint eve>
  block:block_rq_insert                              [Tracepoint eve>
  block:block_rq_issue                               [Tracepoint eve>
  block:block_rq_merge                               [Tracepoint eve>
  block:block_rq_remap                               [Tracepoint eve>
  block:block_rq_requeue                             [Tracepoint eve>
  block:block_sleeprq                                [Tracepoint eve>
  block:block_split                                  [Tracepoint eve>
  block:block_touch_buffer                           [Tracepoint eve>
  block:block_unplug                                 [Tracepoint eve>

```
