
Notes for Pootle FS Git demo
----------------------------


- Everybody has a working Pootle setup, right?
- [Install pootle_fs_git](http://docs.translatehouse.org/projects/pootle/en/latest/features/pootle_fs_install_plugins.html)
- [Setup a Pootle FS git project](http://docs.translatehouse.org/projects/pootle/en/latest/features/pootle_fs_add_project.html)

  - Choose ``git`` backend
  - Use ``git@github.com:translate/pootle_fs_demo.git`` URL
  - Specify ``/<language_code>/<dir_path>/<filename>.<ext>`` mapping
  - Add mapping for ``es_ES`` to ``es``

- [Terms you need to know now](http://docs.translatehouse.org/projects/pootle/en/latest/features/pootle_fs.html#core-concepts)
- The demo itself:

  - ``fetch`` then ``sync`` to ensure we pulled the remote repo translations to Pootle
  - Translate something and ``sync`` (translations are auto-staged)
  - Translate something for **es** then ``sync`` and check in VCS changes go to **es_ES**
  - Translate something else and alter same string in repo, then ``state`` to see conflict

    - Explain the [conflict solving possibilities](http://docs.translatehouse.org/projects/pootle/en/latest/features/using_pootle_fs.html#resolving-conflicts):

      1. Pootle overrides
      2. Filesystem overrides
      3. Filesystem prevails and Pootle becomes suggestion (default)
      4. Pootle prevails and filesystem becomes suggestion

    - Run ``merge`` then ``sync`` (Filesystem prevails and Pootle becomes suggestion)

  - Add new file in repo, ``fetch`` then ``sync``
  - Remove file in repo, ``rm`` then ``sync``
  - How to figure out what to do:

    - Use ``state`` to know what is going on (or if you are in doubt)

  - Changes in ``templates`` are not automatically synced to the project languages, so needs to be [done outside Pootle](http://docs.translatehouse.org/projects/pootle/en/latest/server/project_setup.html#updating-strings-for-existing-project) as before Pootle FS.

- Now everybody pairs and tries to replicate. Ask for help if needed.
