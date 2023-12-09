# Controle de Ônibus Elétrico com Arduino

## Descrição do Projeto

Este repositório contém o código e a documentação para o projeto de controle de ônibus elétrico utilizando um microcontrolador ATMega 328p montado em um circuito próprio. O projeto inclui a simulação do ônibus elétrico em um kit Arduino, com o objetivo de implementar técnicas de controle para otimizar o percurso respeitando as restrições de energia disponível.

## Requisitos do Projeto

### Requisito Funcional

A tarefa de controle do ônibus elétrico requer o cumprimento de um itinerário pré-definido no menor tempo possível, considerando as recargas nos pontos de parada para otimização do uso da bateria.

### Requisito de Sistema

O controlador do sistema é implementado em um circuito montado a partir de materiais fornecidos em laboratório, incluindo o microcontrolador ATMega 328, placa de contatos (protoboard), gravador USBasp, conectores, resistores, capacitores, e um kit Arduino para a simulação.

## Simulador de Ônibus Elétrico

O simulador implementado em Arduino fornece uma plataforma para controle da trajetória do ônibus elétrico ao longo de um itinerário. O "plotter serial" do ambiente Arduino exibe a posição, velocidade e nível de energia do ônibus durante a simulação.

<img width="661" alt="image" src="https://github.com/santoguiia/onibus-eletrico-controle/assets/44483048/3d2c3bc7-6587-4a56-a27d-532ccbc44517">


## Implementação do Simulador em Arduino

O código-fonte do simulador pode ser encontrado [aqui](link-para-o-codigo). Este código utiliza sinais PWM para representar a posição, velocidade e estado da bateria do ônibus. Certifique-se de ler a documentação completa no código para entender a implementação.

<img width="412" alt="image" src="https://github.com/santoguiia/onibus-eletrico-controle/assets/44483048/57c396c0-8db9-4de1-8b9b-23d92f545727">

## Modelo do Ônibus

### Modelo Cinemático


O modelo do ônibus descreve o comportamento cinemático do veículo, relacionando acelerações instantâneas com a velocidade e a posição ao longo do tempo. Supõe-se que
efeitos dinâmicos (atritos, inclinação do trajeto, potência dos motores) sejam tratados pelo sistema mecânico de tal forma que valores de aceleração comandados pelo controlador sejam sempre aplicados ao veículo. Desta forma, o modelo do ônibus é dado por:

<img width="123" alt="image" src="https://github.com/santoguiia/onibus-eletrico-controle/assets/44483048/3b28ff2a-8e6c-4b35-a8e0-b3980177510e">

Portanto, a simulação consiste da integração iterativa da aceleração instantânea a(t) para cálculo da velocidade v(t), e da velocidade para cálculo da posição s(t). A aceleração é calculada por:

<img width="168" alt="image" src="https://github.com/santoguiia/onibus-eletrico-controle/assets/44483048/517021c1-16cf-4ffb-8e9c-3150a3d6334b">


### Modelo de Consumo Energético

O consumo instantâneo de energia é calculado com base na velocidade e na aceleração do ônibus, considerando fatores de consumo e recuperação de energia. Para cálculo do consumo instantâneo de energia do ônibus, usa-se formula ad hoc dada por:

<img width="412" alt="image" src="https://github.com/santoguiia/onibus-eletrico-controle/assets/44483048/a9b5ee88-201f-486f-81b8-e7acdf034023">


## Contribuição

Sinta-se à vontade para contribuir para este projeto. Se encontrar problemas ou tiver sugestões de melhorias, abra uma _issue_ ou envie um _pull request_.
