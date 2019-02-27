---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# 常見問題：SSH 金鑰

## 在哪裡可以找到我的 SSH 金鑰？
{:faq}

SSH 金鑰是裝置所特有，且能在裝置內找到。因為每個作業系統都不同，找到 SSH 金鑰的步驟也是 OS 所特有。若要進一步瞭解在裝置上產生 SSH 金鑰，請參閱關於[產生 SSH 金鑰 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window} 的 GitHub 文章。

## 我可以新增多少 SSH 金鑰至我的帳戶？
{:faq}

您可以將最多 100 個 SSH 金鑰關聯至一個帳戶。獲授權的使用者可以使用 {{site.data.keyword.slportal_full}}，一次[新增 1 個 SSH 金鑰](add-ssh-key.html)。雖然大部分使用者不需要 100 個金鑰，您應該移除任何不需要的金鑰，以確保空間可供更多有效金鑰使用。如需相關資訊，請參閱[移除 SSH 金鑰](remove-ssh-key.html){:new_window}。

## 我沒有看到列出我的實際 SSH 金鑰，但有看到指紋。那是什麼？
{:faq}

與 SSH 金鑰詳細資料一起顯示的指紋，是由系統產生的位元組縮寫序列。指紋比 SSH 金鑰本身短，且用來鑑別或查閱相關聯裝置的公開金鑰。

## 如果我建立或重新載入使用映像檔範本的裝置，SSH 金鑰會延續嗎？
{:faq}

是，同時也否。每個裝置都有唯一的 SSH 金鑰，因此新佈建或重新載入的裝置，其金鑰將與映像檔不同。不過，與 Flex 映像檔或標準映像檔範本相關聯的 SSH 金鑰，會在佈建或重新載入裝置時與裝置相關聯。您也可以在設定程序期間新增金鑰。

