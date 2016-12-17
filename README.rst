===============================================================================
  Online Linguistic Database Ansible Playbook
===============================================================================

Role Variables
===============================================================================

General
-------------------------------------------------------------------------------

- `old_src_dir`: location where the source code repositories are cloned
   (default: user home)


Soft Dependency Installation
-------------------------------------------------------------------------------

- `old_src_install_foma`: install foma/flookup (default: "yes")
- `old_src_install_mitlm`: install MITLM (default: "yes")
- `old_src_install_ffmpeg`: install Ffmpeg (default: "yes")


Version
-------------------------------------------------------------------------------

- `old_src_version`: OLD branch (tag or commit) to install


Reset
-------------------------------------------------------------------------------

- `old_src_reset_db`: set to true to re-create the OLD database (normally at
   runtime using `ansible-playbook` `--extra-vars` switch)
- `old_src_reset_store`: set to true to clear the directory structure in store/
   (normally at runtime using `ansible-playbook` `--extra-vars` switch)
- `old_src_reset_all`: set to true to re-create the OLD database and clear the
   directory structure in store/ (normally at runtime using `ansible-playbook`
   `--extra-vars` switch). If true, it overrides the two vars above.


Remote repository
-------------------------------------------------------------------------------

- `old_src_repo`: OLD repository (default:
  `"https://github.com/jrwdunham/old-pyramid.git"`)



Tags
-------------------------------------------------------------------------------

Tags can be used to control which parts of the playbook to run.

- ``oldsrc-clone``: Checkout OLD source code
- ``oldsrc-osdep``: Install operating system dependencies
- ``foma``: Install foma
- ``tgrep2``: Install TGrep2
- ``mitlm``: Install MITLM
- ``oldsrc-pydep``: Install Python (pip) dependencies
- ``oldinsts``: Create, configure and serve OLD instances


License
-------------------------------------------------------------------------------

AGPLv3
