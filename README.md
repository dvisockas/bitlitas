# Bitlitas

Lietuviška kriptovaliuta

## Reikia

```console
$ cmake build-essential pkg-config libboost-all-dev libssl-dev libzmq3-dev libsodium-dev libreadline6-dev git
```
## Diegimas

```console
$ git clone https://github.com/Bitlitas/bitlitas.git
$ cd bitlitas
$ make (arba make -j1 su vienų core jei mažai ramų)
$ cd build/release/bin
$ ./bitlitasd
```

Daugiau informacijos: `--help`

### Mac OS X
Sudiegiam brew for mac: https://brew.sh

```console
$ sudo wget https://raw.githubusercontent.com/zeromq/cppzmq/master/zmq.hpp -O /usr/local/include/zmq.hpp
$ brew install boost --with-python zmq graphviz
```

## Nauja piniginė

Veikiant jungčiai piniginė yra bitlitas-wallet-cli failas

Rašome norėdami susikurti naują piniginę:
```console
$ ./bitlitas-wallet-cli --generate-new-wallet=piniginesPavadinimas.bin
 ```

Atverti jau sukurtą:
```console
$ ./bitlitas-wallet-cli --wallet=piniginesPavadinimas.bin
```

Norėdami pradėti kasti, rašome `start_mining [branduolių skaičius]`

Daugiau informacijos: `--help`

Nepamirškite išsisaugoti žodžių paslapties ir rakto.

## Jeigų trūksta RAM buildinimui

Sukuriame 2 GB swap failą:
```console
$ sudo fallocate -l 2G /swapfile
$ sudo chmod 600 /swapfile
$ sudo mkswap /swapfile
```
Norėdami uždėti failą, kaip SWAP RAM:
```console
$ sudo swapon /swapfile
```