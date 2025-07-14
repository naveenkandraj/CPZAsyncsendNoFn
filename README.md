# CPZAsyncsendNoFn
Creating Asynchronous tasks for sending notifications



# Sync Notification drawback
in the given synchronous notification logic 
time.sleep(2) # Thread will be executed directly using main tread and it will block the main thread to continue with current TASK
in the **update_task** route blocks the main thread 

#Creating Async Push Model
We need to bypass the load from being executed by the main thread
To implement this process we impose direct usage of threading to handle the push notification process

#Async notification model
threading.Thread() -> it will bypass the load from main thread to prevent the future occuring blokages
I have created method **send_notification_background** for sending the notification using background threads instead active threads.
"daemon=True" this parameter ensures the main_thread(app) won’t prevent shutdown.
Direct task targeting will give us the task enclosure assurance using background thread 

