# wxwork_finance_sdk_wrapper

企业微信-会话内容存档PHP扩展

./php7-wxwork-finance-sdk文件夹来自https://github.com/pangdahua/php7-wxwork-finance-sdk

## 文档
https://github.com/pangdahua/php7-wxwork-finance-sdk

## 安装
```shell
# 安装ext-wxwork_finance_sdk
installExtWxworkFinanceSdk(){
  ln -s /lib/libc.musl-x86_64.so.1 /lib/ld-linux-x86-64.so.2 \
  && cd /tmp \
  && curl -SL "https://github.com/oh-stone/wework-chatdata-sdk/archive/v0.1.0.tar.gz \
  && mkdir -p wxwork_finance_sdk \
  && tar -xf wxwork_finance_sdk.tar.gz -C wxwork_finance_sdk --strip-components=1 \
  && ( \
      cd wxwork_finance_sdk/php7-wxwork-finance-sdk \
      && phpize \
      && ./configure --with-wxwork-finance-sdk=/tmp/wxwork_finance_sdk/C_sdk \
      && make && make install \
  ) \
  && cp /tmp/wxwork_finance_sdk/C_sdk/libWeWorkFinanceSdk_C.so /usr/local/lib/libWeWorkFinanceSdk_C.so \
  && echo "extension=wxwork_finance_sdk.so" > /etc/php7/conf.d/50_wxwork_finance_sdk.ini \
  && php --ri wxwork_finance_sdk
}
