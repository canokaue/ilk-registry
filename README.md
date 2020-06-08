 # Ilk Registry

 A publicly-modifiable registry of `ilk`'s in the Dai Stablecoin System.

## Requirements

* [Dapptools](https://github.com/dapphub/dapptools)

## About

Provides an on-chain list of `ilk` types in the DSS system.

Useful for external contracts which need to iterate over the on-chain ilk types and/or access information about a particular ilk.

* Modify the registry

    * `add(address joinAdapter)`: Add a new ilk to the registry by passing the Join Adapter address. The adapter must be live on mainnet and can not already be included in the registry.

    * `remove(bytes32 ilk)`: Remove an ilk from the registry if it's adapter has been caged.

* Get information from the registry

    * `get()`: return a `bytes32[]` of available ilk types.
    * `get(uint256 pos)`: get the `bytes32` ilk type from an indexed position in the array.
    * `get(uint256 start, uint256 end)`: returns a `bytes32[]` of a portion of the complete list.
    * `count()`: return number of ilks as `uint256`
    * `pos()`: the location in the `ilks` array for this `ilk`
    * `gem()`: the `address` of the ilk's token contract
    * `pip()`: the `address` of the ilk's pip contract
    * `join()`: the `address` of the ilk's join adapter
    * `flip()`: the `address` of the ilk's flipper contract
    * `dec()`: the number of decimals for an `ilk` as `uint256`


## Testing

Configure `ETH_RPC_URL` for mainnet testing and run `./test-ilk-registry.sh`
