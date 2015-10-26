Ansible skip test
=================

Run with with::

    ansible-playbook -i hosts site.yml -t alpha

Result::

    PLAY ***************************************************************************
    
    TASK [setup] *******************************************************************
    ok: [localhost]
    
    TASK [role-alpha : This is the Alpha Role] *************************************
    ok: [localhost] => {
        "changed": false, 
        "msg": "Alpha Role"
    }
    
    TASK [role-alpha : Include in alpha] *******************************************
    included: /home/drybjed/src/projects/devel/roles/ansible-skip-test/roles/role-alpha/tasks/in_alpha.yml for localhost
    
    TASK [role-alpha : Inside include in alpha] ************************************
    ok: [localhost] => {
        "changed": false, 
        "msg": "Included in Alpha role"
    }
    
    PLAY ***************************************************************************
    
    TASK [setup] *******************************************************************
    ok: [localhost]
    
    TASK [role-beta : Include in Beta] *********************************************
    included: /home/drybjed/src/projects/devel/roles/ansible-skip-test/roles/role-beta/tasks/in_beta.yml for localhost
    
    PLAY RECAP *********************************************************************
    localhost                  : ok=6    changed=0    unreachable=0    failed=0   

