# ORE 挖礦

## 1. 查詢獎勵
ore --rpc http://116.202.32.188:8899 --keypair ~/.config/solana/id.json rewards

## 2. 手動執行挖礦
screen -dmS ore_4 bash -c "while true; do ore --rpc http://116.202.32.188:8899 --keypair /root/.config/solana/id4.json --priority-fee 1 mine --threads 4; echo '?程异常退出，等待重启' >&2; sleep 1; done"

## 3. 激活地址
solana account 錢包地址

## 4. 查詢錢包
solana balance --keypair /root/.config/solana/id4.json

## 5. solana 建立新錢包地址
solana-keygen new --outfile /root/.config/solana/id5.json

## 6. solana 轉帳 確認可以成功
solana transfer 接收SOL的錢包地址 0.002 --keypair /root/.config/solana/id3.json --url http://116.202.32.188:8899 --allow-unfunded-recipient

## 7. 確認錢包地址
solana-keygen pubkey /root/.config/solana/id4.json

## 8. 確認私鑰與錢包地址的關係是否正確
solana-keygen verify 根據上面的指令拿到的地址或稱公鑰 /root/.config/solana/id4.json

## 9. 查詢獎勵
ore --rpc http://116.202.32.188:8899 --keypair ~/.config/solana/id2.json rewards

## 10. 領取挖礦收益
ore --rpc http://116.202.32.188:8899 --keypair ~/.config/solana/id2.json --priority-fee 70000000 claim

## 11. 轉移 $ORE 到指定帳戶
spl-token transfer --owner /root/.config/solana/id4.json --url http://116.202.32.188:8899 oreoN2tQbHXVaZsr3pf66A48miqcBXCDJozganhEJgz ALL 接收代幣的錢包地址 --fund-recipient
