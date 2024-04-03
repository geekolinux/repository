## Repository role for all common Linux distributions
Features of my repository role:
- [x] Modify repository for Redhat based machines
- [x] Modify repository for Oracle
- [x] Modify repository for Debian based machines
- [ ] Modify repository for SUSE
- [x] Enable/Disable repositories for all supported distributions
- [x] Add Third-party repository 


## Requirements
Be sure your operating system can access the internet to download the repositories. 
  
## Usage
Add repository on Debian based machines
```yaml
repo_apt_manage_repositories:
  - repo: "deb http://nginx.org/packages/mainline/debian/ stretch nginx"
    state: present
    filename: /etc/apt/sources.list.d/nginx
```
Delete repository on Debian based machines
```yaml
repo_apt_manage_repositories:
  - repo: "deb http://nginx.org/packages/mainline/debian/ stretch nginx"
    state: absent
    filename: /etc/apt/sources.list.d/nginx
```
Add nginx signing key to Debian based machines
```yaml
repo_apt_add_key: []
  - url: "http://nginx.org/keys/nginx_signing.key"
    dest: "/etc/apt/trusted.gpg.d/nginx.asc"
    mode: "0644"
```

Add repository on Redhat based and Oracle machines
```yaml
repo_yum_manage_repositories:
  - name: nginx
    repo_url: http://nginx.org/packages/rhel/$releasever/$basearch/
    description: Nginx Repo
    gpgcheck: true
    gpgkey: https://nginx.org/keys/nginx_signing.key
    state: present
    enabled: true
```

Delete repository on Redhat based and Oracle machines
```yaml
repo_yum_manage_repositories:
  - name: nginx
    repo_url: http://nginx.org/packages/rhel/$releasever/$basearch/
    description: Nginx Repo
    gpgcheck: true
    gpgkey: https://nginx.org/keys/nginx_signing.key
    state: absent
    enabled: true
```

Deactivate repository on Redhat based and Oracle machines
```yaml
repo_yum_manage_repositories:
  - name: nginx
    repo_url: http://nginx.org/packages/rhel/$releasever/$basearch/
    description: Nginx Repo
    gpgcheck: true
    gpgkey: https://nginx.org/keys/nginx_signing.key
    state: present
    enabled: false
```


## License
[MIT License](https://opensource.org/license/MIT)

## Author
I like to give linux administrators an guidance and solving their hand-made problems with the new generation of automatization.
I´m open for any improvements, please contact if you have an feature requests to make my repository better. Feedback is always welcome, just write me 
on my email: geekolinuxexpert@proton.me

Enjoy my art,

Geeko
