PHP software for the ALMA front end test and measurement system.

Installation
------------

 1. Clone to a directory, say, fetms.
 2. Create symlinks in `fetms` to an extjs ver 3.4 directory, which can reside almost anywhere (although apparently must be on the same server).:
 `ln -s ../ext ext (can't use until ext dir restored)`
 or
 `ln -s  ../../ext-3.3.1-JCModified  ext`
`ls -s ../../ext-4.1.1a ext4`
 3. Create the dir `ALMA-FETMS-www` and add a symlink in it to an `io` directory that has the these rights `drwxrwsr-x`:
`ln -s ../../io test_datafiles`
 4. Also create another symlink in `fetms` to the same `io` directory:
  `ln -s ../io test_datafiles`
 5. Change `config_main.php` to show the following:
  `case "webtest2.cv.nrao.edu":
        $rootdir_url = "https://webtest2.cv.nrao.edu/php/ntc/ws-jee/fetms";`
 
 6. Change `fetms\dbConnect\dbConnect.php` to show the following:
`case "webtest2.cv.nrao.edu": 
require_once("/home/webtest.cv.nrao.edu/conf/jee-dbConnect.conf");`
