**Multi-User DBMS Architectures**
- Teleprocessing
	- Puts heavy processing burden on centralized mainframe; User interfaces simple but mainframe expensive
- File-Server
	- Issues with concurrency, security; Each individual workstation has its own DBMS. Workstations expensive
- Client-Server
	- One copy of DBMS in server; Clients have some processing capability to generate queries. Server is only responsible for DBMS, increasing performance
	- Wider access to existing databases
	- Reduction of hardware cost (client-side not as expensive as workstation). Reduction in communication costs. File-server requires us to transfer files to workstation to process query; client-server only returns result of query. Reduces network traffic
	- Increased consistency (sole DBMS)

**Client-Server Architectures (topologies):**
- Two-Tier Client-Server
	- First Tier: Client; Tasks: 
		- User interface (view) 
		- Main data processing logic
	- Second Tier: Database Server; Tasks: 
		- Server-side validation
		- Database access
	- Alternative two-tier client-server topologies:
		- Single client, single server
		- Multiple clients, single server
		- Multiple clients, multiple servers

Fat Clients: Too much work on client-side. We can reduce the cost of clients using:

**N-Tier Client Architectures**
- First tier: Client (thin)
	- User interface
- Second Tier: Application Server
	- Business logic, data processing logic
- Third tier: Database Server
	- Data validation, database access
- Advantages:
	- "Thin" clients are less expensive
	- Application maintenance is centralized
	- Easier to modify or replace one tier without affecting others (tier independence)
	- Separating business logic from database functions makes it easier to implement load balance
- Application Server examples:
	- Web logic server (e.g. OC4J)
	- JEE/J2EE
	- JBoss (Redhat)
	- .NET (Microsoft)
	- Oracle application server

**Middleware**
- Software that mediates other software, facilitates communication among disparate applications. 
- Six main types
	- Asynchronous remote procedure calls (RPC)
	- Synchronous RPCs
	- Publish/Subscribe
	- Message-oriented
	- Object-oriented broker
	- SQL-oriented data access
- Transaction Processing Monitor as middle tier of a three-tier client-server architecture. Advantages:
	- Transaction routing
	- Managing distributed transactions
	- Load balancing
	- Funneling
	- Increased reliability
- Web Service
	- Software system that supports interoperable machine-to-machine interaction over network
- Service-Oriented Architecture (SOA)
	- Architecture for building applications that implement business processes as sets of services

**Distributed DBMSs**
- Distributed Database:
	- Data distribution and replication among distributed databases
	- Copy of data may be stored (replicated) at multiple sites for better accessibility (transmission speeds), performance, and reliability. Data split into fragments
		- Horizontal (row, instance) replication
		- Vertical (by attribute) replication
	- Logically interrelated collection of shared data (and data description) and databases physically distributed over a computer network. e.g. Sites (nodes of communication network graph) could include Chicago, New York, SF, etc. Different sites could have different subsets of whole company's data replicated. e.g. New York could have NY and SF data replicated. Good practice is to have one site's data replicated at another to increase reliability
- Distributed DBMS:
	- Software system that permits management of distributed DB, makes distribution transparent to users
- Distributed Processing:
	- One centralized database (unlike distributed database), but distributed computation