# Helsemelding Kafka Manager

Tjenesten er tilgjengelig i dev-miljø via URL:
https://helsemelding-kafka-manager.intern.dev.nav.no

## Legg til topic

For å få innsyn i en ny topic:

1. Legg til et nytt element i en konfigurasjon i [kafka-manager-dev.yaml](.nais/kafka-manager-dev.yaml), for eksempel:
```
{

  "name": "<team>.<topic>",
  "location": "AIVEN",
  "keyDeserializerType": "STRING",
  "valueDeserializerType": "STRING"
}
```
2. Gi kafka-manager lesetilgang til topic i definisjonen av selve topicen, for eksempel:
```
spec:
  acl:
    - access: read
      application: kafka-manager
      team: helsemelding
```
3. Deploy topicen og kafka-manager på nytt.

## Creds
https://github.com/navikt/helsemelding-kafka-manager
