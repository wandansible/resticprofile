Ansible role: resticprofile
===========================

Install and configure resticprofile and restic for managing backups.

Role Variables
--------------

```
ENTRY POINT: *main* - Install and configure resticprofile and restic for managing backups

Options (= indicates it is required):

- resticprofile_arch_map  Mapping of the possible values of
                           ansible_facts.architecture to the
                           resticprofile package architectures
          default: null
          type: dict

- resticprofile_archive_extension  File extension for the
                                    resticprofile package archive
          default: tar.gz
          type: str

- resticprofile_bin_dir  Directory for the resticprofile binaries
          default: /opt/resticprofile
          type: str

- resticprofile_checksum_filename  Filename for the resticprofile
                                    package checksums file on github
          default: checksums.txt
          type: str

- resticprofile_checksum_type  The resticprofile package checksum
                                type
          default: sha256
          type: str

- resticprofile_clean_src_dir  Remove old downloaded archive files
                                from resticprofile src directory
          default: true
          type: bool

- resticprofile_cli_tools  List of CLI tool binaries that should have
                            symlinks created in /usr/local/bin/
          default: [resticprofile]
          type: list

- resticprofile_config  Contents of the resticprofile config file, as
                         string or dict
          default: null
          type: raw

- resticprofile_config_dir  Directory for resticprofile configuration
          default: /etc/resticprofile
          type: str

- resticprofile_config_file  Filename for resticprofile config file
          default: profiles.yml
          type: str

- resticprofile_github_org  Name of organisation for resticprofile
                             github repository
          default: creativeprojects
          type: str

- resticprofile_github_repo  Name of resticprofile github repository
          default: resticprofile
          type: str

- resticprofile_github_token  Optional bearer token to use to
                               authenticate with api.github.com
          default: ''
          type: str

- resticprofile_install  If true, install resticprofile
          default: true
          type: bool

- resticprofile_restic_arch_map  Mapping of the possible values of
                                  ansible_facts.architecture to the
                                  restic package architectures
          default: null
          type: dict

- resticprofile_restic_archive_extension  File extension for the
                                           restic package archive
          default: bz2
          type: str

- resticprofile_restic_bin_dir  Directory for the restic binaries
          default: /opt/restic
          type: str

- resticprofile_restic_checksum_filename  Filename for the restic
                                           package checksums file on
                                           github
          default: SHA256SUMS
          type: str

- resticprofile_restic_checksum_type  The restic package checksum
                                       type
          default: sha256
          type: str

- resticprofile_restic_clean_src_dir  Remove old downloaded archive
                                       files from restic src directory
          default: true
          type: bool

- resticprofile_restic_cli_tools  List of CLI tool binaries that
                                   should have symlinks created in
                                   /usr/local/bin/
          default: [restic]
          type: list

- resticprofile_restic_config_dir  Directory for restic configuration
                                    files
          default: /etc/resticprofile/restic
          type: str

- resticprofile_restic_config_files  List of restic configuration
                                      files to create
          default: null
          elements: dict
          type: list
          options:

          = config  Config file contents
            type: str

          = name  Name of config file
            type: str

- resticprofile_restic_github_org  Name of organisation for restic
                                    github repository
          default: restic
          type: str

- resticprofile_restic_github_repo  Name of restic github repository
          default: restic
          type: str

- resticprofile_restic_gpg_keyserver  GPG keyserver to use for
                                       fetching restic public key
          default: hkps://keyserver.ubuntu.com
          type: str

- resticprofile_restic_install  If true, install restic
          default: true
          type: bool

- resticprofile_restic_signature_filename  Filename for the restic
                                            checksums signature file
                                            on github
          default: SHA256SUMS.asc
          type: str

- resticprofile_restic_src_dir  Directory for the downloaded restic
                                 src archive
          default: /opt/restic/src
          type: str

- resticprofile_restic_src_files  List of files to extract from the
                                   source archive
          default: [restic]
          elements: str
          type: list

- resticprofile_restic_strip_components  Strip NUMBER leading
                                          components from file names
                                          on extraction
          default: 1
          type: int

- resticprofile_restic_update_randomized_delay  Delay the restic
                                                 update timer by a
                                                 random time up to
                                                 this value or empty
                                                 string for no delay
          default: 6h
          type: str

- resticprofile_restic_update_time  How often to update restic,
                                     accepts a systemd time, see
                                     https://www.freedesktop.org/software/systemd/man/latest/systemd.time.html,
                                     or "never"
          default: daily
          type: str

- resticprofile_restic_version  Version to install (use "latest" for
                                 the latest version)
          default: latest
          type: str

- resticprofile_src_dir  Directory for the downloaded resticprofile
                          src archive
          default: /opt/resticprofile/src
          type: str

- resticprofile_src_files  List of files to extract from the source
                            archive
          default: [resticprofile]
          elements: str
          type: list

- resticprofile_strip_components  Strip NUMBER leading components
                                   from file names on extraction
          default: 0
          type: int

- resticprofile_template_dir  Directory for resticprofile templates
          default: /etc/resticprofile/templates
          type: str

- resticprofile_template_files  List of resticprofile template files
                                 to create
          default: null
          elements: dict
          type: list
          options:

          = config  Template file contents
            type: str

          = name  Name of template file
            type: str

- resticprofile_update_randomized_delay  Delay the resticprofile
                                          update timer by a random
                                          time up to this value or
                                          empty string for no delay
          default: 6h
          type: str

- resticprofile_update_time  How often to update resticprofile,
                              accepts a systemd time, see
                              https://www.freedesktop.org/software/systemd/man/latest/systemd.time.html,
                              or "never"
          default: daily
          type: str

- resticprofile_version  Version to install (use "latest" for the
                          latest version)
          default: latest
          type: str
```

Installation
------------

This role can either be installed manually with the ansible-galaxy CLI tool:

    ansible-galaxy install git+https://github.com/wandansible/resticprofile,main,wandansible.resticprofile
     
Or, by adding the following to `requirements.yml`:

    - name: wandansible.resticprofile
      src: https://github.com/wandansible/resticprofile

Roles listed in `requirements.yml` can be installed with the following ansible-galaxy command:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

    - hosts: all
      roles:
        - role: wandansible.resticprofile
          become: true
          vars:
            resticprofile_config: |
              version: "2"

              global:
                default-command: version

              groups:
                full-backup:
                  continue-on-error: true
                  profiles:
                    - root
                  schedules:
                    backup:
                      at: daily

              profiles:
                default:
                  repository: "/srv/restic"

                root:
                  inherit: default
                  backup:
                    exclude-caches: true
                    exclude:
                      - /var/log
                      - /var/cache
                      - /var/tmp
                      - /var/run
                      - /tmp
                      - /dev
                      - /sys
                      - /run
                      - /proc
                    one-file-system: true
                    source:
                      - /
                  retention:
                    after-backup: true
                    before-backup: false
                    keep-daily: 1
                    keep-weekly: 1
                    keep-monthly: 1
                    keep-yearly: 1
                    prune: true
