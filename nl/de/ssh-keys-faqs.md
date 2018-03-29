---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Häufig gestellte Fragen (FAQs): SSH-Schlüssel

## Wo finde ich meinen SSH-Schlüssel?

SSH-Schlüssel sind gerätespezifisch und innerhalb des Geräts angegeben. Da jedes Betriebssystem anders ist, sind die Schritte zum Finden des SSH-Schlüssels betriebssystemspezifisch. Weitere Informationen zum Generieren eines SSH-Schlüssels für ein Gerät finden Sie im GitHub-Artikel unter [SSH-Schlüssel generieren![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://help.github.com/articles/generating-ssh-keys#platform-windows){: new_window}.

## Wie viele SSH-Schlüssel kann ich meinem Konto hinzufügen?

Sie können einem Konto bis zu 100 SSH-Schlüssel zuordnen. Benutzer mit der entsprechenden Berechtigung können jeweils [1 SSH-Schlüssel hinzufügen](add-ssh-key.html), indem sie das {{site.data.keyword.slportal_full}} verwenden. Wenngleich die wenigsten Benutzer 100 Schlüssel benötigen, sollten Sie alle nicht benötigten Schlüssel entfernen, um sicherzustellen, dass genügend Platz für gültige Schlüssel zur Verfügung steht. Weitere Informationen finden Sie unter [SSH-Schlüssel entfernen](remove-ssh-key.html){:new_window}.

## Mein tatsächlicher SSH-Schlüssel wird mir in der Liste nicht angezeigt, dafür aber ein Fingerabdruck. Was hat das zu bedeuten?

Der Fingerabdruck, der zusammen mit den Details für einen SSH-Schlüssel angezeigt wird, ist eine abgekürzte Byte-Sequenz, die vom System generiert wurde. Der Fingerabdruck ist kürzer als der eigentliche SSH-Schlüssel und wird zur Authentifizierung oder zum Suchen des öffentlichen Schlüssels für das zugeordnete Gerät verwendet.

## Wenn ich ein Gerät erstelle oder neu lade, das eine Imagevorlage verwendet, werden die SSH-Schlüssel dann übernommen?

Ja und nein. Jedes Gerät besitzt einen eindeutigen SSH-Schlüssel, weshalb der Schlüssel für das neu bereitgestellte oder neu geladene Gerät von dem Image abweichen wird.  Allerdings werden SSH-Schlüssel, die entweder einem Flex Image oder einem Standard-Image zugehörig sind, dem Gerät zugeordnet, wenn dieses bereitgestellt oder neu geladen wird. Sie können auch Schlüssel während des Einrichtungsprozesses hinzufügen.
