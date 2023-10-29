# Welcome to the Verilog Playground!

## Overview

Practice Verilog and SystemVerilog on our playground:
1. Write some code
2. Click Run
3. Check the logs
4. Success! Interact with the simulator!

Website: https://verilog-playground.github.io

![Animation](https://github.com/verilog-playground/art/blob/ea775d95664f92fbba2eddffff865a58d73a8608/animation.gif)

## Repositories

**Back-end:** [infrastructure](https://github.com/verilog-playground/infrastructure)

**Front-end:** [verilog-playground.github.io](https://github.com/verilog-playground/verilog-playground.github.io)

## How it Works?

The front-end uses [React](https://react.dev) and was created using [create-react-app](https://create-react-app.dev). It is hosted on [GitHub Pages](https://pages.github.com).

The back-end infrastructure is hosted on Amazon Web Services (AWS) and primarily consists of API Gateway and Lambda functions. The system is managed using the AWS Cloud Development Kit (CDK), which is an Infrastructure as Code (IaC) framework.

The simulation itself runs client-side. After the user submits the code, a Lambda function is triggered by API Gateway to start the transpilation process. This process first converts the Verilog/SystemVerilog code to C++ using [Verilator](https://www.veripool.org/verilator), and then converts the C++ code to JavaScript using [Emscripten](https://emscripten.org). With the resulting JavaScript code in hand, the browser uses the `eval` function to interact with the simulation. The user receives logs about the process in real time, thanks to a WebSocket connection between the browser and the API Gateway.

## Acknowledgements

- Many thanks to my professors [Elmar Melcher](https://ieeexplore.ieee.org/author/37265255200) and [Joseana Fechine](https://scholar.google.com.br/citations?user=Uf098wYAAAAJ) for their support and incentive since the beginning of the project.
- Many thanks to the [Verilator](https://www.veripool.org/verilator) and [Emscripten](https://emscripten.org) developers for making it possible to run the simulation client-side, thereby enabling the creation of this project.
