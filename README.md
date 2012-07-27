## What's ngx_mruby
ngx_mruby - to provide an alternative to mod_mruby for nginx.

nginx modules can be implemeted by mruby scripts on nginx installed ngx_mruby.

## How to use (experiment)

* �ޤ���Github���饽�������������ɤ��ޤ���

    git clone git://github.com/matsumoto-r/ngx_mruby.git

* �����ơ�config�ե�����򳫤��ơ�mruby�����󥹥ȡ��뤵��Ƥ���Path���ѹ����Ʋ��������ͤξ��ϰʲ��Τ褦�ˤ��Ƥ��ޤ���

    mruby_root=/usr/local/src/mruby

* nginx1.2.2stable���������ɤ��ޤ���

    wget http://nginx.org/download/nginx-1.2.2.tar.gz

* ��������ɸ塢Ÿ�����ưʲ��Υ��ޥ�ɤ�ngx_mruby��⥸�塼��Ȥ��ƻ��ꤷ��nginx���Τ�Τ򥳥�ѥ��뤷�ޤ���

    ./configure --add-module=/usr/local/src/ngx_mruby --prefix=/usr/local/nginx122
    make
    sudo make install

* ����ѥ���塢nginx.conf������˰ʲ��Τ褦�������ä��ޤ���

    location /mruby {
        mrubyHandler /usr/local/nginx122/html/hello.mrb;
    }

* ���ꤷ��mruby������ץȡ�/usr/local/nginx122/html/hello.mrb�ˤ˰ʲ��Υ᥽�åɤ򵭽Ҥ��ޤ���

    Nginx.rputs("hello mruby world for nginx.")

* �Ǥϡ�nginx��ư���ޤ���

    /usr/local/nginx122/sbin/nginx

* �����ơ�http://example.com/mruby�˥����������Ƥߤޤ��礦����example.com�򼫥ɥᥤ����֤������Ʋ�������

    hello mruby world for nginx.

��ɽ�����줿�������Ǥ����褦������mruby world for nginx�ء���
