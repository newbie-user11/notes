**Objective**
Familiarisation with `redis-cli`.

**Redis**
- Redis or Remote Dictionary Server is an open-source advanced NoSQL key-value used for databasing, caching, and message broking. 
- It is for short term storage for fast retrieval of information. 
- Install it by running the command `sudo apt install redis-tools`.

**Solving The Box**
- Follow directions from [[Meow]] to set up openvpn connection and perform ping check, followed by `nmap -sV` for enumeration of target machine IP. For this box, this step will take up to one hour.
- Use command `redis-cli --help` for a list of possible functions using `redis-cli`.
- Understand that flag -h will allow connection to host (IP address). Use command `redis-cli -h` to connect to this port.
- Then open `select 0`. If OK, run command `keys *` for a list of databases on the port. Now capture the flag.