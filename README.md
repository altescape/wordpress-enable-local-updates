wordpress-enable-local-updates
==============================

To enable updates locally on OSX do the following. Complete all steps and change ownership back to you otherwise you won't be able to edit anything.

----

1. ##### Add following code to wp-config.php

  ~~~
  // Make sure to comment the line below when live
  define('FS_METHOD','direct');
  ~~~


2. ##### Change ownership and permissions of entire wp-content folder to apache owner
  sudo chown -R _www wp-content; sudo chmod -R g+w wp-content


3. ##### Change ownership back to originial owner and change permissions back to default 755
  sudo chown -R michaelwatts:wheel wp-content; sudo chmod -R 755 wp-content


4. ##### Change ownership and permissions of uploads directory back to apache owner so _www can upload/edit
  sudo chown -R _www wp-content/uploads; sudo chmod -R g+w wp-content/uploads


@todo: See if you can skip changing everything but the themes folder as that is where most editing is done, so wouldn't need to change and change back everytime.
