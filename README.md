What this does:

1. Checks DNS for the API and apps host
2. Checks port 6443 (or whatever you type) on the API host and port 443 (or whatever you type) on the apps host. If either fails, the play stops
3. Prompts you for credentials, iDRAC host, and comma-separated image lists.
4. Logs in to Red Hat registries.
5. Loops over and pulls every image you listed for each registry.
6. Curls the iDRAC endpoint and console.redhat.com, showing HTTP status codes.
7. Logs out of the Red Hat registries at the end.


How to Run:
Replace Variables in vars.yml file
ansible-playbook -i your_inventory validationtest.yml
