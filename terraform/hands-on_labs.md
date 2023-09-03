# Hands-on Labs

### More than Certified - Derek Morgan
1. Create a Node-RED docker container.
2. Output container name and its IP address.
3. Next use join function to output `<IP>:<port>` instead of just IP address.
4. Add another Node-RED docker container along with steps# 2 & 3. 
5. Use random to rename the first container.
6. Use count to rename both containers and remove duplicate code block for second container.
     - Make necessary changes in output blocks. 
8. Use splat expression to output container name. 
9. Use for expression to output `<IP>:<port>`.
10. Delete a docker container created outside of Terraform config.
11. Fix Terraform state ($ terraform state list) when a docker container was deleted outside of Terraoform config.
12. Set external port as a variable for Node-RED container.
     - Input value in the CLI
     - Input value as an environment variable
     - Set a default value
13. Set both container count and internal port as variables with default value.
14. Create a validation for internal port to always be 1880.
15. Create a validation for external port to be in the part range 0 - 65535.
16. Create seperate terraform files for variables and output.
17. Override default variable value with another terraform file.
18. How to create and use multiple tfvars file for different envrionments.
19. Set external port as a sensitive variable.
20. Use local-exec provisioner as a null resource to bind a local directory in the container.
21. Set a group of external ports to be used (instead of single port) and use local values to setup container count (enternal port validation will fail).
22. Fix external port validation.
23. Remove hard coded host_path for volumes and make it dynamic.
24. Pretending there are two envs (dev and prod), use latest Node-RED image for dev env and latest-minimal for prod.
25. Setup different sets of external ports for dev (1980, 1981) and prod (1880, 1881) environments.
