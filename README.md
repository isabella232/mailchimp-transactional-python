# Mailchimp Transactional — Python

The official Python client library for the Mailchimp Transactional API (v1)

## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

If the python package is hosted on GitHub, you can install directly from GitHub

```sh
pip install git+https://github.com/mailchimp/mailchimp-transactional-python.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/mailchimp/mailchimp-transactional-python.git`)

Then import the package:
```python
import mailchimp_transactional
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import mailchimp_transactional
```

## Quick Start

Please follow the [installation procedure](#installation--usage) and then run the following:

## Quick Start

```python
import mailchimp_transactional as MailchimpTransactional
from mailchimp_transactional.api_client import ApiClientError

try:
  mailchimp = MailchimpTransactional.Client('YOUR_API_KEY')
  response = mailchimp.users.ping()
  print('API called successfully: %s'.format(response))
except ApiClientError as error:
  print('An exception occurred: {}'.format(error.text))
```

## Sending Requests
All requests are sent via POST and accept a single argument as the request body parameter.
```python
mailchimp.templates.publish({ name: 'My Template' });
```

## Output Formats
Optionally, you can set the default response format for **all requests** to one of the following:
- `json` *(default)*
- `xml`
- `php`
- `yaml`

```python
mailchimp.set_default_output_format('xml');
```

You can also set the response format for a **single request** by passing in a special `outputFormat` param to the request body.
```python
mailchimp.senders.list({ outputFormat: 'php' });
```

## API Endpoints

All URIs are relative to *https://mandrillapp.com/api/1.0*

| Method | Endpoint |
| ---------- | -------- |
| **exports.activity** | /exports/activity |
| **exports.info** | /exports/info |
| **exports.list** | /exports/list |
| **exports.rejects** | /exports/rejects |
| **exports.whitelist** | /exports/whitelist |
| **inbound.add_domain** | /inbound/add-domain |
| **inbound.add_route** | /inbound/add-route |
| **inbound.check_domain** | /inbound/check-domain |
| **inbound.delete_domain** | /inbound/delete-domain |
| **inbound.delete_route** | /inbound/delete-route |
| **inbound.domains** | /inbound/domains |
| **inbound.routes** | /inbound/routes |
| **inbound.send_raw** | /inbound/send-raw |
| **inbound.update_route** | /inbound/update-route |
| **ips.cancel_warmup** | /ips/cancel-warmup |
| **ips.check_custom_dns** | /ips/check-custom-dns |
| **ips.create_pool** | /ips/create-pool |
| **ips.delete** | /ips/delete |
| **ips.delete_pool** | /ips/delete-pool |
| **ips.info** | /ips/info |
| **ips.list** | /ips/list |
| **ips.list_pools** | /ips/list-pools |
| **ips.pool_info** | /ips/pool-info |
| **ips.provision** | /ips/provision |
| **ips.set_custom_dns** | /ips/set-custom-dns |
| **ips.set_pool** | /ips/set-pool |
| **ips.start_warmup** | /ips/start-warmup |
| **messages.cancel_scheduled** | /messages/cancel-scheduled |
| **messages.content** | /messages/content |
| **messages.info** | /messages/info |
| **messages.list_scheduled** | /messages/list-scheduled |
| **messages.parse** | /messages/parse |
| **messages.reschedule** | /messages/reschedule |
| **messages.search** | /messages/search |
| **messages.search_time_series** | /messages/search-time-series |
| **messages.send** | /messages/send |
| **messages.send_raw** | /messages/send-raw |
| **messages.send_template** | /messages/send-template |
| **metadata.add** | /metadata/add |
| **metadata.delete** | /metadata/delete |
| **metadata.list** | /metadata/list |
| **metadata.update** | /metadata/update |
| **rejects.add** | /rejects/add |
| **rejects.delete** | /rejects/delete |
| **rejects.list** | /rejects/list |
| **senders.add_domain** | /senders/add-domain |
| **senders.check_domain** | /senders/check-domain |
| **senders.domains** | /senders/domains |
| **senders.info** | /senders/info |
| **senders.list** | /senders/list |
| **senders.time_series** | /senders/time-series |
| **senders.verify_domain** | /senders/verify-domain |
| **subaccounts.add** | /subaccounts/add |
| **subaccounts.delete** | /subaccounts/delete |
| **subaccounts.info** | /subaccounts/info |
| **subaccounts.list** | /subaccounts/list |
| **subaccounts.pause** | /subaccounts/pause |
| **subaccounts.resume** | /subaccounts/resume |
| **subaccounts.update** | /subaccounts/update |
| **tags.all_time_series** | /tags/all-time-series |
| **tags.delete** | /tags/delete |
| **tags.info** | /tags/info |
| **tags.list** | /tags/list |
| **tags.time_series** | /tags/time-series |
| **templates.add** | /templates/add |
| **templates.delete** | /templates/delete |
| **templates.info** | /templates/info |
| **templates.list** | /templates/list |
| **templates.publish** | /templates/publish |
| **templates.render** | /templates/render |
| **templates.time_series** | /templates/time-series |
| **templates.update** | /templates/update |
| **urls.add_tracking_domain** | /urls/add-tracking-domain |
| **urls.check_tracking_domain** | /urls/check-tracking-domain |
| **urls.list** | /urls/list |
| **urls.search** | /urls/search |
| **urls.time_series** | /urls/time-series |
| **urls.tracking_domains** | /urls/tracking-domains |
| **users.info** | /users/info |
| **users.ping** | /users/ping |
| **users.ping2** | /users/ping2 |
| **users.senders** | /users/senders |
| **webhooks.add** | /webhooks/add |
| **webhooks.delete** | /webhooks/delete |
| **webhooks.info** | /webhooks/info |
| **webhooks.list** | /webhooks/list |
| **webhooks.update** | /webhooks/update |
| **whitelists.add** | /whitelists/add |
| **whitelists.delete** | /whitelists/delete |
| **whitelists.list** | /whitelists/list |


## Additional Client Libraries

Mailchimp Transactional libraries are available in the following languages:

<div>
  <a href="https://github.com/mailchimp/mailchimp-transactional-node">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_node.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-transactional-php">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_php.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-transactional-ruby">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_ruby.png?raw=true" width="44" height="44">
  </a>
  <a href="https://github.com/mailchimp/mailchimp-transactional-python">
  <img src="https://github.com/mailchimp/mailchimp-client-lib-codegen/blob/master/resources/images/lang_python.png?raw=true" width="44" height="44">
  </a>
</div>
