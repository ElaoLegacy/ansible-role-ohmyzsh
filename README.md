WARNING: This role is no longer maintained !!!
==============================================

You are strongly encouraged to switch to the new roles stack on https://github.com/ElaoInfra
--------------------------------------------------------------------------------------------

By the way, this role will remain available on https://github.com/ElaoLegacy
----------------------------------------------------------------------------


Ansible Role - Oh My Zsh
========================

An oh-my-zsh role for elao symfony standard vagrant box


Requirements
------------

This role only run on elao symfony standard vagrant box. See https://vagrantcloud.com/elao/symfony-standard-debian


Role Variables
--------------

    elao_ohmyzsh_users:     # Array of users
      foo:                     # User name
        theme:   robbyrussell  # User theme
        plugins: ['git']       # User plugins
        prompt:  null          # User prompt
        cwd:     null          # User cwd


Example Playbook
----------------

    - hosts: servers
	  vars:
	    elao_ohmyzsh_users:
	      root:
	        theme:   pygmalion
	        plugins: ['debian', 'common-aliases']
	      vagrant:
	        theme:   pygmalion
	        plugins: ['debian', 'common-aliases', 'git', 'composer', 'symfony2']
	        prompt:  '%{$fg[cyan]%}%n%{$fg[red]%}@%{$fg[cyan]%}%m %{$fg_bold[red]%} %{$fg_bold[green]%}%p %{$fg[cyan]%}%c %{$fg_bold[blue]%}$(git_prompt_info)%{$fg_bold[blue]%} % %{$reset_color%}'
	        cwd:     /var/www
      roles:
         - { role: elao.ohmyzsh }


License
-------

MIT


Author Information
------------------

http://www.elao.com/
