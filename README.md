Spree Mercado Pago Payment Method
=================================

This project is compatible with spree 3.2.0 and Rails 5

```
gem 'spree_mercado_pago', '~> 3.2.0.rc2', git: "git@github.com:lucasruroken/spree_mercado_pago.git"
```

If you want to use this gem with spree 2.3 or 2.4, you should use the original repo:
```
gem 'spree_mercado_pago', git: "git@github.com:manuca/spree_mercado_pago.git"
```

inside your project run

```
bundle exec rails g spree_mercado_pago:install
```

to import assets and migrations.

APP
---
Create new Application at https://applications.mercadopago.com/

Usage
-----
- Add a new payment method in the admin panel of type Spree::PaymentMethod::MercadoPago
- After adding the payment method you will be able to configure your Client ID and Client Secret (provided by Mercado Pago).
- Get credentials at https://www.mercadopago.com/mla/account/credentials

IPN
---

For IPN you need to configure the notification URL in Mercado Pago's site. The notification URL will be `http[s]://[your_domain]/mercado_pago/ipn`. Please review Mercado Pago's documentation at http://developers.mercadopago.com/ for the correct place where to configure IPN notification URLs.
- Set config for ipn at https://www.mercadopago.com.ar/ipn-notifications

Pending Work
------------

- Configurable currency

Testing
-------
- If you want to test checkout in sandbox mode, you can obtain fakes users and credit cards https://www.mercadopago.com.ar/developers/es/solutions/payments/basic-checkout/test/

rspec
-----

- clone this repo
- execute `bundle`
- execute `rake test_app` to build a dummy app directory inside specs
- execute `bundle exec rspec spec`
