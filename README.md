Slurm Job Exporter
==================

This role installs and configures the Prometheus [Slurm Job
Exporter](https://github.com/guilbaults/slurm-job-exporter/).

Role Variables
--------------

See [defaults/main.yml](defaults/main.yml).

To use a fork of the default GitHub project:

    # Define git repository
    slurm_job_exporter_git_repo: "https://github.com/abergeron/slurm-job-exporter.git"

To install a new release:

    slurm_job_exporter_version: "v0.0.14-mila"

To define an alternate installation path:

    slurm_job_exporter_path: "/path/to/slurm-job-exporter"

To add arguments to the executables:

    slurm_job_exporter_arguments: "--reporter-type=prometheus"

Example Playbook
----------------

Install and configure the exporter:

    - hosts: computes
      vars:
        slurm_job_exporter_version: v0.4.5
      tasks:
        - name: Import role mila.slurm_job_exporter
          ansible.builtin.import_role:
            name: mila.slurm_job_exporter
          tags: role::slurm_job_exporter

