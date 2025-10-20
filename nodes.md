# ⚠️ Running List of (Potentially) Problematic Nodes


|      Node       |         Reference          |
| :-------------: | :------------------------: |
| `x4002c2s1b0n0` | 🚨[^slow-vaino-2025-08-23] |
| `x4717c7s2b0n0` | 🚨[^slow-vaino-2025-08-23] |
| `x4514c6s1b0n0` | 🚧[^slow-vaino-2025-08-23] |
| `x4208c0s5b0n0` | 🚧[^slow-vaino-2025-08-23] |
| `x4311c0s5b0n0` | 🚧[^slow-vaino-2025-08-23] |
| `x4102c4s5b0n0` | 🚧[^slow-vaino-2025-08-23] |
| `x4314c7s0b0n0` | 🚧[^slow-vaino-2025-08-23] |
| `x4608c3s1b0n0` | 🚧[^slow-vaino-2025-08-23] |
| `x4711c3s6b0n0` | 🚧[^slow-vaino-2025-08-23] |

[^slow-vaino-2025-08-23]:
    
    <details closed><summary>[<b>2025-08-23</b>] (Väinö Hatanpää, on Slack):</summary>

    - [Report](https://cels-anl.slack.com/archives/C058HKVJ0QL/p1755957183678639):
      
      > I did some full machine PyTorch benchmarking and there were some
      > troublemaker nodes.  
      > These were >10% slower than others (sample size 1-3, could be randomness,
      > but some were reoccurring):
      >
      > ```bash
      > x4514c6s1b0n0 x4208c0s5b0n0 x4311c0s5b0n0 x4102c4s5b0n0 x4314c7s0b0n0 x4608c3s1b0n0 x4711c3s6b0n0
      > ```
      >
      > And these two were hanging with some communication calls, every time I tried:
      >
      > ```bash
      > x4002c2s1b0n0 x4717c7s2b0n0
      > ```

    </details>
