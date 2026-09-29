# acc-message-sync-fix
This patch and diff correct a race condition between four separate systems that can break multiple features, such as undo delete, when custom code pushes messages into oc.thread.messages. Basically, it adds a "canonical" version check against the message feed to make sure stale renders are not performed.

# ACC Message Sync Fix

This patch and diff correct a race condition between four separate systems
that can break multiple features, such as undo delete, when custom code
pushes messages into `oc.thread.messages`.

Basically, it adds a "canonical" version check against the message feed
to make sure stale renders are not performed.

## Included fixes

- Race condition caused by custom code pushing messages into `oc.thread.messages`
- Stale message render prevention
- Message-list synchronization between the main thread and custom-code iframe
- Undo delete fixes resulting from the original message-system overhaul

## Compatibility

This patch was developed against a personal ACC fork and may not apply
cleanly to other ACC forks. Forks with modified message/rendering code
may require manual adaptation.

The `.patch` file contains the changes in a form that Git can attempt
to apply, while `diff.txt` provides a readable reference for manually
porting the changes.
