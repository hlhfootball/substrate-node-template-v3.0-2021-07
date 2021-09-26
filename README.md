# Substrate Node Template Benchmark
## 编译
```sh
cargo build --release --features runtime-benchmarks
```
输出如下
![image](https://github.com/hlhfootball/substrate-node-template-v3.0-2021-07/blob/master/.screenshots/compile.png)

# Benchmark
```sh
./target/release/node-template benchmark --chain dev --execution=wasm --wasm-execution=compiled --pallet pallet_template --extrinsic do_something --steps 50 --repeat 20 --template=./.maintain/frame-weight-template.hbs --output=./pallets/template/src/weights.rs
```
输出如下
```sh
Pallet: "pallet_template", Extrinsic: "do_something", Lowest values: [], Highest values: [], Steps: [20], Repeat: 50
Median Slopes Analysis
========
-- Extrinsic Time --

Model:
Time ~=     24.6
    + s        0
              µs

Reads = 0 + (0 * s)
Writes = 1 + (0 * s)
Min Squares Analysis
========
-- Extrinsic Time --

Data points distribution:
    s   mean µs  sigma µs       %
    0     24.69     0.193    0.7%
    5      24.3     0.253    1.0%
   10     23.83     0.312    1.3%
   15     23.54     0.111    0.4%
   20     23.59      0.08    0.3%
   25     23.59     0.149    0.6%
   30     24.29     1.052    4.3%
   35     28.21     1.614    5.7%
   40      29.7      0.14    0.4%
   45     26.39     0.082    0.3%
   50     26.26     0.068    0.2%
   55     26.35     0.104    0.3%
   60     26.26     0.061    0.2%
   65     26.23     0.078    0.2%
   70     23.88     0.965    4.0%
   75     23.33     0.077    0.3%
   80     22.83      0.29    1.2%
   85     23.31     0.177    0.7%
   90     23.38     0.073    0.3%
   95     23.19     0.247    1.0%
  100     23.26     0.308    1.3%

Quality and confidence:
param     error
s         0.002

Model:
Time ~=    25.43
    + s        0
              µs

Reads = 0 + (0 * s)
Writes = 1 + (0 * s)
```
# Chain Spec 生成
```sh
# Export the local chain spec to json
./target/release/node-template build-spec --disable-default-bootnode --chain local > ./.chain-spec/customSpec.json
```

```sh
./target/release/node-template build-spec --chain=./.chain-spec/customSpec.json --raw --disable-default-bootnode > ./.chain-spec/customSpecRaw.json
```


