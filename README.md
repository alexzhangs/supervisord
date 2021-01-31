# supervisord

Supervisor init.d script for Amazon Linux AMI.

Tested with:

* supervisor 4.0.3 on
  * Amazon Linux AMI
* supervisor 4.0.3 and 4.2.1 on
  * Amazon Linux 2 AMI

Originally forked from: https://gist.github.com/mhayes/866900

## Why does this repo exist?
1. `supervisor` is availabe in
   [yum repo](http://supervisord.org/installing.html#installing-a-distribution-package),
   an init.d script like this(not same) is also included. But
   currently(2019-06) the version is still 2.1, far behind the current
   stable version 4.0.3. Also version 2.1 supports python 2.6 only,
   doesn't work with python 2.7.
   
2. Installing `supervisor` with pip is recommended by [official
document](http://supervisord.org/index.html). But these's no init.d
script included in the package.


## Installation

```
git clone https://github.com/alexzhangs/supervisord
cp -a supervisord/supervisord /etc/init.d/
chmod 755 /etc/init.d/supervisord
chkconfig --add supervisord
```

Or more directly way:

```
curl https://raw.githubusercontent.com/alexzhangs/supervisord/master/supervisord -o /etc/init.d/supervisord
chmod 755 /etc/init.d/supervisord
chkconfig --add supervisord
```

## Usage

```
service supervisord start
service supervisord stop
```
