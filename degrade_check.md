# degrade check (デグレチェック)
Checking whether a code change, bug fix, or new feature has **unintentionally broken existing functionality**.

This is essentially the same concept as a regression check or **regression test** (リグレッションテスト / 回帰テスト).

## Example in embedded development

Suppose you modify:

- CAN communication
- UART driver
- Motor control logic

After the change, you don't only test the modified function. 

You also check related functions to ensure nothing else was affected:

- System boot
- Communication interfaces
- Error handling
- Existing control functions
- Memory usage
- Real-time performance

If a previously working feature stops working after the modification, that is called a: **デグレ (degrade)** or **デグレーション (degradation/regression)**.
