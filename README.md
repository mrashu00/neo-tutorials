Creating a Smart Contract on Neo X

1. Introduction

This tutorial will guide you through creating a smart contract on Neo X using the Neo blockchain platform.

2. Prerequisites

Basic knowledge of programming in C# or Python.

Install Neo Blockchain Toolkit.

Set up Neo Express and Visual Studio Code.


3. Setting Up the Environment

1. Install .NET SDK:

sudo apt install dotnet-sdk-6.0


2. Install Neo Blockchain Toolkit:

dotnet tool install -g Neo.BlockchainToolkit


3. Install Visual Studio Code and Neo extensions:

Neo Smart Contract Debugger.

Neo Blockchain Toolkit Extension.




4. Writing the Smart Contract

1. Create a new contract project:

dotnet new neo-contract


2. Open the contract file (Contract.cs):

using Neo.SmartContract.Framework;
using Neo.SmartContract.Framework.Services;

namespace HelloWorld
{
    public class Contract : SmartContract
    {
        public static string Main(string name)
        {
            return $"Hello, {name}";
        }
    }
}



5. Deploy the Contract

1. Compile the contract:

dotnet build


2. Start Neo Express:

neo-express start


3. Deploy the contract:

neo-express contract deploy Contract.nef



6. Test the Contract

1. Invoke the contract:

neo-express contract invoke Contract --method Main --args ["World"]
