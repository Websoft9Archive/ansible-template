- name: Change postgresql databases directory
  lineinfile:
      dest: /etc/postgresql/{{postgresql_version}}/main/postgresql.conf
      regexp: "data_directory = '/var/lib/postgresql/{{postgresql_version}}/main'"
      line: "data_directory = '/data/pgsql'"
      state: present
