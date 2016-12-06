old-src
===============================================================================

Online Linguistic Database installation from source.

Role Variables
-------------------------------------------------------------------------------

### General

- `old_src_dir`: location where the source code repositories are cloned
   (default: user home)

### Projects

- `old_src_install_foma`: install foma/flookup (default: "yes")
- `old_src_install_mitlm`: install MITLM (default: "yes")
- `old_src_install_ffmpeg`: install Ffmpeg (default: "yes")

### Version

- `old_src_version`: OLD branch (tag or commit) to install

### Reset

- `old_src_reset_db`: set to true to re-create the OLD database (normally at
   runtime using `ansible-playbook` `--extra-vars` switch)
- `old_src_reset_store`: set to true to clear the directory structure in store/
   (normally at runtime using `ansible-playbook` `--extra-vars` switch)
- `old_src_reset_all`: set to true to re-create the OLD database and clear the
   directory structure in store/ (normally at runtime using `ansible-playbook`
   `--extra-vars` switch). If true, it overrides the two vars above.


### Remote repository

- `old_src_repo`: OLD repository (default:
  `"https://github.com/jrwdunham/old-pyramid.git"`)


#### SSL (when using gunicorn/nginx)

- `old_src_ssl`: configure the OLD to use SSL (default:`false` though should be
   changed to `true`)
- `old_src_ssl_include_acme_chlg_loc`: Include ACME challenge location file
  (`acmetool-location.conf`) in nginx configuration file, provided by role
  https://github.com/jrwdunham/ansible-acmetool (default:`false`)
- `old_src_ssl_fullchain`: (no default provided, should be defined in the
  playbook or host_vars if SSL enabled)
- `old_src_ssl_privkey`: (no default provided, should be defined in the
  playbook or host_vars if SSL enabled)


Tags
-------------------------------------------------------------------------------

Tags can be used to control which parts of the playbook to run, especially on
updates. Note that if something is disabled with the [role
variables](#role-variables), it won't be run even if the tag is enabled.

- `oldsrc-ss`: OLD install
    - `oldsrc-ss-clone`: Checkout source code
    - `oldsrc-ss-osdep`: Install operating system dependencies
    - `oldsrc-ss-pydep`: Install Python dependencies (with pip)
    - `oldsrc-ss-osconf`: Configure operating system
    - `oldsrc-ss-code`: Install source code
    - `oldsrc-ss-db`: Configure database
    - `oldsrc-ss-websrv`: Configure webserver


License
-------------------------------------------------------------------------------

AGPLv3
