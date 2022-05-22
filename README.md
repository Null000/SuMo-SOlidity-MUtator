# SuMo
SuMo is a mutation testing tool for Solidity Smart Contracts. It features 25 Solidity-specific mutation operators, as well as 19 traditional operators.

Note that [ReSuMo](https://github.com/MorenaBarboni/ReSuMo/tree/main/src) advances the functionalities of SuMo through:
1. a static, file-level regression testing mechanism for evolving projects
2. the usage of the Trivial Compiler Equivalence (TCE) for automatically detecting and discarding mutant equivalencies


## Installation

To run SuMo you must: 
1. Install the required dependencies with ```npm install```.
1. Specify the path to your project directory and the path to your ```contracts``` directory in the ```sumo\src\operator.config.json``` file. 
2. Specify the ```test``` and ```compile``` scripts in your ```package.json``` file.
3. Make sure that the contracts to be mutated pass all the tests. If at least one of the tests fails, the mutation testing process cannot be run.

You can exclude a specific contract from the mutation process by specifying its path in the
```sumo\src\operator.config.json``` file.

## Usage

Before starting the mutation process you can choose which mutation operators must be applied:
* ```sumo list``` shows the currently enabled mutation operators
* ```sumo enable``` enables all the mutation operators
* ```sumo enable ID``` enables the mutation operator ID
* ```sumo disable``` disables all the mutation operators
* ```sumo disable ID``` disables the mutation operator ID

Once everything is set up you can use:
* ```sumo preflight``` To view all the available mutations
* ```sumo test``` To launch the mutation testing process

## Results
SuMo automatically creates a ```.sumo``` folder in the root directory of the project. <br/>
At the end of the mutation testing process the folder will contain:
* ```report.txt``` Test report
* ```\alive``` Mutants that survived testing
* ```\killed``` Mutants killed by tests

## Mutation Operators

### Traditional Operators
| Operator | Description |
| ------ | ------ |
| ACM| Argument Change of overloaded Method call |
| AOR | Assignment Operator Replacement |
| BCRD | Break and Continue Replacement and Deletion |
| BLR | Boolean Literal Replacement |
| BOR | Binary Operator Insertion |
| CBD | Catch Block Deletion |
| CSC | Conditional Statement Change |
| ER | Enum Replacemet |
| ECS | Explicit Conversion to Smaller type |
| HLR | Hexadecimal Literal Replacement |
| ICM | Increments Mirror |
| ILR | Integer Literal Replacement |
| LCS | Loop Statement Change |
| OLFD | Overloaded Function Deletion |
| ORFD | Overridden Function Deletion |
| SKI | Super Keyword Insertion |
| SKD | Super Keyword Deletion |
| SLR | String Literal Replacement |
| UORD | Unary Operator Replacement and Deletion |

### Solidity Operators
|Operator | Description |
| ------ | ------ |
| AVR | Address Value Replacement |
| CSC | Contract Constructor Deletion |
| DLR | Data Location Keyword Replacement |
| DOD | Delete Operator Deletion |
| ETR | Ether Transfer function Replacement |
| EED |  Event Emission Deletion |
| EHC | Exception Handling Change |
| FVR | Function Visibility Replacement |
| GVR | Global Variable Replacement |
| MCR | Mathematical and Cryptographic function Replacement |
| MOD | Modifier Deletion |
| MOI | Modifier Insertion |
| MOC | Modifier Order Change |
| MOC | Modifier Order Change |
| MOR | Modifier Replacement |
| PKD | Payable Keyword Deletion |
| RSD | Return Statement Deletion |
| RVS | Return Values Swap |
| SFD | Selfdestruct Deletion |
| SFI | Selfdestruct Insertion |
| SFR | SafeMath Function Replacement |
| SCEC | Switch Call Expression Casting |
| TOR | Transaction Origin Replacement |
| VUR | Variable Unit Replacement |
| VVR | Variable Visibility Replacement |


### Publications

To cite SuMo, please use the following:

```
@inproceedings{9463055,
  author={Barboni, Morena and Morichetta, Andrea and Polini, Andrea},
  booktitle={2021 IEEE/ACM International Conference on Automation of Software Test (AST)}, 
  title={SuMo: A Mutation Testing Strategy for Solidity Smart Contracts}, 
  year={2021},
  pages={50-59}
  } 
```
