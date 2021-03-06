# CiviCRM: Evaluate a release candidate

## Check the build

Navigate to http://download.civicrm.org/latest and verify that the RC has a
release with a suitable timestamp. 

(If the RC is missing, inspect the records for https://test.civicrm.org/job/CiviCRM-Publish/)

## Create the hydra

In case there have been significant changes in the CMS integrations, in
distmaker, or in the installer, you should double-check that the tarballs
and installers still work as expected.

If you have a system with `civibuild`, then you can use the related command
`civihydra` to spin up empty sites and download the tarballs.  For example:

```
civihydra create https://download.civicrm.org/latest/civicrm-RC-drupal.tar.gz
civihydra create https://download.civicrm.org/latest/civicrm-RC-wordpress.zip
civihydra create https://download.civicrm.org/latest/civicrm-RC-joomla.zip
civihydra create https://download.civicrm.org/latest/civicrm-RC-backdrop.tar.gz
# civihydra create https://download.civicrm.org/latest/civicrm-RC-drupal6.tar.gz
```

or build all of them in one command:

```
civihydra create https://download.civicrm.org/latest/civicrm-RC-drupal.tar.gz https://download.civicrm.org/latest/civicrm-RC-wordpress.zip https://download.civicrm.org/latest/civicrm-RC-joomla.zip https://download.civicrm.org/latest/civicrm-RC-backdrop.tar.gz
```

The `civihydra` command will print out instructions to complete each installation manually.

If you missed the instructions, display them again by running `civihydra show`.

## WIP

We should be defining more processes to evaluate RCs.
