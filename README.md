## Introduction
<h3>Protocol Name: Ondo Finance</h3>
<h3>Category: RWA Tokenization</h3>
<h3>Smart Contract: Ondo</h3>

## Function Analysis
<h2>Function Name: I will be focusing on a constructor rather than a function</h2>
<h2>Block Explorer Link: <a href="https://etherscan.io/address/0x1915A8dE08A92b846dF7C845e140E4b0714820bd#code">Block Explorer Contract Source code</a></h2>
<h2>Function Code: </h2>    
  <p>
    
    constructor(address globals_, address implementation_, address initializer_, address tokenMigrator_) {
        _setAddress(GLOBALS_SLOT, globals_);
        _setAddress(IMPLEMENTATION_SLOT, implementation_);

        ( bool success_, ) = initializer_.delegatecall(abi.encodeWithSelector(
            IMapleTokenInitializerLike(initializer_).initialize.selector,
            tokenMigrator_,
            IGlobalsLike(globals_).mapleTreasury()
        ));

        require(success_, "MTP:INIT_FAILED");
    }
  </p>

  <h2>Used Encoding</h2>
