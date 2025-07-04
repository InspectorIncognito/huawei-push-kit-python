This project is a fork from https://github.com/HMS-Core/hms-push-serverdemo-python. In order to maintain this project the structure of the original repository is kept as close as the original as possible.

The main changes are the following:
- A new module called huawei_push_kit_python was created with an `__init__.py` file inside with the parts of the original module that we want to expose.
- All the imports inside python/src/push_admin files were modified to have an absolute import with python37 as the main module.
- Setup file was deleted.
- `__init__.py` file inside push_admin was emptied.

The current exposed methods and classes are the following:
```
send_message(message, validate_only=False, app_id=None, verify_peer=False):
    """
        Sends the given message Huawei Cloud Messaging (HCM)
        :param message: An instance of ``messaging.Message``.
        :param validate_only: A boolean indicating whether to run the operation in dry run mode (optional).
        :param app_id: app id parameters obtained by developer alliance applying for Push service (optional).
        :return: SendResponse
        Raises:
            ApiCallError: If an error occurs while sending the message to the HCM service.
    """
```
```
class Message(object):
    """A message that can be sent Huawei Cloud Messaging.

    Args:
        data: A string value.
        notification: An instance of ``messaging.Notification`` (optional).
        android: An instance of ``messaging.Android`` (optional).
        apns: APNS related message definition
        web_push: Web Push related message definition
        token: token list, must be tuple (optional).
        topic: message topic, must be string (optional).
        condition: message condition, must be string (optional).
    """
    def __init__(self, data=None, notification=None, android=None, apns=None, web_push=None, token=None,
                 topic=None, condition=None):
```
