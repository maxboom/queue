# Installation guide:

```bash
git clone git@github.com:maxboom/queue.git .
```
```bash
docker-compose up -d
```
```bash
docker-compose exec php bash
```
**In docker container:**
```bash
cd skeleton/
```
```bash
/usr/bin/composer install
```
```bash
php bin/console d:m:m
```

## Usage
### Action to send message: http://localhost:9150/mailer
### Consume messages: 
```bash php bin/console messenger:consume async -vv```

### Working with failed messages:
Mock the failed message via changing
```yaml
routing:
  'Symfony\Component\Mailer\Messenger\SendEmailMessage': failed
```
in ```messenger.yaml```

And consume failed messages:
```bash
php bin/console messenger:failed:retry -vv
```