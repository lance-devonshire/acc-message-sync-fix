# acc-message-sync-fix
This patch and diff correct a race condition between four separate systems that can break multiple features, such as undo delete, when custom code pushes messages into oc.thread.messages. Basically, it adds a "canonical" version check against the message feed to make sure stale renders are not performed.
