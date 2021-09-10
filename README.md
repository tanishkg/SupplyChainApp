# SupplyChainApp
This is Ethereum blockchain technology based Supply chain management decentralized application.

To test this project install Ganache and be sure to copy the addresses for A‐G from your own Ganache addresses at the beginning and throughout this file.
If you use a text editor, you can do a Find and Replace to speed up this step.

A‐0: 0xba1e5E81a62218a79C6E0FC49Edb3B52df17B063
B‐1: 0xd22Ae9602a0f4D4BD42c6EE471f538a9EE531aAB
C‐2: 0x4f47D66725EFabd09C14a31eA43737D97F130efe
D‐3: 0x2b4beb7aE56386448eBD8bA1C4f0641127274f03
E‐4: 0x08113369cB87F08c4A905451895E61e45581f08C
F‐5: 0x5039a3CA1D7F8653efA06035cF56Db99Da44F516
G‐6: 0x569e0d0c60aFBcFa48f703C5702Dc1DeF984f67D

supplyChain.deployed().then(function(instance) {return instance });

// Create 3 manufacturer participants (A, B, C)
supplyChain.deployed().then(function(instance) {return instance.addParticipant("A","passA","0xba1e5E81a62218a79C6E0FC49Edb3B52df17B063","Manufacturer") });
supplyChain.deployed().then(function(instance) {return instance.addParticipant("B","passB","0xd22Ae9602a0f4D4BD42c6EE471f538a9EE531aAB","Manufacturer") });
supplyChain.deployed().then(function(instance) {return instance.addParticipant("C","passC","0x4f47D66725EFabd09C14a31eA43737D97F130efe","Manufacturer") });

// Create 2 supplier participants (D, E)
supplyChain.deployed().then(function(instance) {return instance.addParticipant("D","passD","0x2b4beb7aE56386448eBD8bA1C4f0641127274f03","Supplier") });
supplyChain.deployed().then(function(instance) {return instance.addParticipant("E","passE","0x08113369cB87F08c4A905451895E61e45581f08C","Supplier") });

// Create 2 consumer participants (F, G)
supplyChain.deployed().then(function(instance) {return instance.addParticipant("F","passF","0x5039a3CA1D7F8653efA06035cF56Db99Da44F516","Consumer") });
supplyChain.deployed().then(function(instance) {return instance.addParticipant("G","passG","0x569e0d0c60aFBcFa48f703C5702Dc1DeF984f67D","Consumer") });

// Get participant details
supplyChain.deployed().then(function(instance) {return instance.getParticipant(0)});
supplyChain.deployed().then(function(instance) {return instance.getParticipant(1)});
supplyChain.deployed().then(function(instance) {return instance.getParticipant(2)});
supplyChain.deployed().then(function(instance) {return instance.getParticipant(3)});
supplyChain.deployed().then(function(instance) {return instance.getParticipant(4)});
supplyChain.deployed().then(function(instance) {return instance.getParticipant(5)});
supplyChain.deployed().then(function(instance) {return instance.getParticipant(6)});


// Create 6 products 100, 101 (owned by A), 200, 201 (owned by B), 300, 301 (owned C)

supplyChain.deployed().then(function(instance) {return instance.addProduct(0, "ABC", "100", "123", 11) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(0, "DEF", "101", "456", 12) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(1, "GHI", "200", "789", 13, {from:"0xd22Ae9602a0f4D4BD42c6EE471f538a9EE531aAB"}) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(1, "JKL", "201", "135", 14, {from:"0xd22Ae9602a0f4D4BD42c6EE471f538a9EE531aAB"}) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(2, "MNO", "300", "357", 15, {from:"0x4f47D66725EFabd09C14a31eA43737D97F130efe"}) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(2, "PQR", "301", "759", 16, {from:"0x4f47D66725EFabd09C14a31eA43737D97F130efe"}) });


// Get product details
supplyChain.deployed().then(function(instance) {return instance.getProduct(0) });
supplyChain.deployed().then(function(instance) {return instance.getProduct(1) });
supplyChain.deployed().then(function(instance) {return instance.getProduct(2) });
supplyChain.deployed().then(function(instance) {return instance.getProduct(3) });
supplyChain.deployed().then(function(instance) {return instance.getProduct(4) });
supplyChain.deployed().then(function(instance) {return instance.getProduct(5) });

// Move products along supply chain: Manufacturer=> Supplier=> Supplier=> Consumer
supplyChain.deployed().then(function(instance) {return instance.newOwner(0, 3, 0, {from: "0xba1e5E81a62218a79C6E0FC49Edb3B52df17B063"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(1, 3, 3, {from: "0xd22Ae9602a0f4D4BD42c6EE471f538a9EE531aAB"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(2, 3, 4, {from: "0x4f47D66725EFabd09C14a31eA43737D97F130efe"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(0, 3, 1, {from: "0xba1e5E81a62218a79C6E0FC49Edb3B52df17B063"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(2, 4, 5, {from: "0x4f47D66725EFabd09C14a31eA43737D97F130efe"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(1, 4, 2, {from: "0xd22Ae9602a0f4D4BD42c6EE471f538a9EE531aAB"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 6, 4, {from: "0x2b4beb7aE56386448eBD8bA1C4f0641127274f03"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 4, 1, {from: "0x2b4beb7aE56386448eBD8bA1C4f0641127274f03"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 4, 3, {from: "0x2b4beb7aE56386448eBD8bA1C4f0641127274f03"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(4, 5, 2, {from: "0x08113369cB87F08c4A905451895E61e45581f08C"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 4, 0, {from: "0x2b4beb7aE56386448eBD8bA1C4f0641127274f03"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(4, 6, 0, {from: "0x08113369cB87F08c4A905451895E61e45581f08C"}) });
supplyChain.deployed().then(function(instance) {return instance.newOwner(4, 5, 3, {from: "0x08113369cB87F08c4A905451895E61e45581f08C"}) });

supplyChain.deployed().then(function(instance) {return instance.getProvenance(0) });
supplyChain.deployed().then(function(instance) {return instance.getProvenance(1) });
supplyChain.deployed().then(function(instance) {return instance.getProvenance(2) });
supplyChain.deployed().then(function(instance) {return instance.getProvenance(3) });
supplyChain.deployed().then(function(instance) {return instance.getProvenance(4) });
supplyChain.deployed().then(function(instance) {return instance.getProvenance(5) });
