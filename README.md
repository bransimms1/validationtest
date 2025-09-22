What this does:

1. Checks DNS for the API and apps host
2. Checks port 6443 (or whatever you type) on the API host and port 443 (or whatever you type) on the apps host. If either fails, the play stops
3. Validate DNS + UDP/123 and do an ntpdate -q against your NTP server
4. Logs in to Red Hat registries.
5. Loops over and pulls every image you listed for each registry.
6. Curls the iDRAC endpoint and collects endpoint MAC addresses
7. Curls console.redhat.com, showing HTTP status codes.
8. Logs out of the Red Hat registries at the end.


How to Run:
1. Replace Variables in vars.yml file
2. ansible-playbook -i your_inventory validation_test.yml
