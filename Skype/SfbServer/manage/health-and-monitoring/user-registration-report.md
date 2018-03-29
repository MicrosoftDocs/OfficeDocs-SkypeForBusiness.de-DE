---
title: Bericht über Benutzerregistrierung in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Zusammenfassung: Informationen Sie zu den Bericht über Benutzerregistrierung in Skype für Business Server 2015.'
ms.openlocfilehash: fcf1640b3d8b87664de060ae5866b830ceea3d3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="user-registration-report-in-skype-for-business-server-2015"></a>Bericht über Benutzerregistrierung in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den Bericht über Benutzerregistrierung in Skype für Business Server 2015.
  
Der Bericht über Benutzerregistrierung bietet eine Übersicht über die Benutzeraktivität Anmeldung, insbesondere Informationen über die Anzahl der Benutzer, die Skype für Business Server 2015 während eines angegebenen Zeitraums (stündlich, täglich, wöchentlich, monatlich) angemeldet. Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält. Es kann nicht der angemeldete Benutzer ermittelt werden. Überwachungsberichte bieten keine Informationen über die bestimmte Benutzer Skype für die Business Server 2015 verwenden (und nicht sind, welche). Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.
  
Bei der Bereitstellung von Informationen zu Benutzeranmeldungen macht der Bericht über Benutzerregistrierung zwei erhebliche Unterschiede. Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen. Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Firewall Ihres Unternehmens anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind). Externe Anmeldungen darstellen, Benutzer, die von außerhalb der Firewall über einen Edge-Server (beispielsweise eine von einem Internet angemeldeten Benutzers, die als externe Anmeldung Café zählt) angemeldet. Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.
  
Darüber hinaus Notizen der Bericht über Benutzerregistrierung, wie viele aktive Benutzer während eines bestimmten Zeitraums vorhanden waren. Ein aktiver Benutzer ist ein Benutzer, der Teil in eine Sofortnachrichtensitzung (Instant Messaging), nimmt einen Skype für Business Server Besprechung beteiligt, vorgenommen oder empfangen ein Telefonanrufs oder andernfalls Skype für Business Server in diesem Zeitraum verwendet. Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht genutzt haben.
  
## <a name="accessing-the-user-registration-report"></a>Zugreifen auf den Bericht über Benutzerregistrierung

Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Optimale Nutzung des Berichts über Benutzerregistrierung

Nachdem Sie Skype, für Business Server eine häufig gestellte bereitgestellt haben Frage ist dies: Wie finde ich heraus, wenn meine Benutzer tatsächlich dieser neue Technologie verwenden? Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung der Frage helfen. Um zu bestimmen, ob Benutzer Skype für die Business Server verwenden, müssen Sie zwei Dinge tun. Rufen Sie zunächst den Wert der Metrik „Eindeutige angemeldete Benutzer“ im Bericht über Benutzerregistrierung ab. Dieser Wert erfahren Sie, wie viele verschiedene Einzelpersonen Skype für Business Server angemeldet.
  
Demgegenüber zeigt die Metrik Anmeldungen insgesamt wie insgesamt oft jeder Skype für Business Server angemeldet. Angenommen Sie, dass Ken Myer Skype für Business Server fünf verschiedenen Zeiten an einem Tag angemeldet. In diesem Fall zählt Jan Sachweh als fünf separate Anmeldesitzungen in der Metrik „Anmeldungen insgesamt“, aber nur als ein angemeldeter Benutzer in der Metrik „Eindeutige angemeldete Benutzer“. Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an. Beispielsweise ein Benutzer kann melden Sie sich mit ihrem Desktopcomputer ihrem Laptopcomputer, und er kann als IP-Telefon, das automatisch zu Skype für Business Server angemeldet haben. In diesem Beispiel gibt es einen eindeutigen Benutzer mit drei Anmeldungen.
  
Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.
  
|**User**|**Anmeldezeitpunkt**|
|:-----|:-----|
|Ken Myer  <br/> |07.07.2015 08:45  <br/> |
|Ken Myer  <br/> |07.07.2015 08:46  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:17  <br/> |
|Ken Myer  <br/> |07.07.2015 09:22  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:31  <br/> |
   
Insgesamt fanden fünf Anmeldungen statt, es sind jedoch nur zwei eindeutige angemeldete Benutzer vorhanden: Ken Myer (der sich dreimal angemeldet hat) und Pilar Ackerman (die sich zweimal angemeldet hat). Darin besteht der Unterschied zwischen Anmeldungen und eindeutigen angemeldeten Benutzern.
  
Zusätzlich zu die Anzahl der eindeutigen Anmeldungen näher kennen, müssen Sie die Gesamtzahl der Benutzer wissen, wer für die Skype für Business Server aktiviert wurden. Dass der Wert abgerufen werden kann, indem Sie die Skype für Business Server-Verwaltungsshell öffnen und den folgenden Windows PowerShell-Befehl ausführen:
  
```
(Get-CsUser).Count
```

Wenn der vorstehende Befehl gibt den Wert 1,236 zurück und eindeutige angemeldete Benutzer Metrik gibt ein Durchschnittswert 667, der ein wenig über die Hälfte der Benutzer für aktivieren vorschlägt Skype für Unternehmen sind tatsächlich anmeldet, an das System jeden Tag (das ist 667 geteilt durch 1,236, also ungefähr 54 %).
  
> [!CAUTION]
> Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben. Bereits im System angemeldete Benutzer werden nicht erfasst. Wenn zum Beispiel die Metrik „Eindeutige angemeldete Benutzer“ 667 Anmeldungen anzeigt und insgesamt 1.236 Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer im System anmeldet. Nehmen wir jedoch an, 300 Benutzer waren bereits am System angemeldet, als Sie mit der Überprüfung der Anmeldedaten begonnen haben. Würde bedeuten, dass Sie tatsächlich fast 1.000 Benutzer Skype für Business Server, was bedeuten würde, dass die, die sich näher auf 80 % der Benutzer angemeldet waren angemeldet hat. 
  
Vergleichen Sie auch den Wert „Eindeutige angemeldete Benutzer“ mit dem Wert der Metrik „Eindeutige aktive Benutzer“. Die eindeutige aktive Benutzer Metrik erfahren Sie, wie viele eindeutige Benutzer tatsächlich Skype für Business Server verwendet: ein Telefonanrufs vorgenommen, sie einen Skype für Business Server Besprechung verknüpft oder sie an einer Sofortnachrichtensitzung mitgewirkt. Dies ist die nützliche Informationen, da Skype für Business Server 2015 konfiguriert werden kann, um jedes Mal automatisch gestartet, ein Benutzer Windows startet. Aus diesem Grund müssen Sie eine große Anzahl von Benutzern möglicherweise, die automatisch Skype für Unternehmen beim Anmelden sie melden Sie sich an den Windows jeden Tag, aber für Business Server diesen Zeitraum Skype nie tatsächlich verwenden.
  
Die Metrik eindeutige aktive Benutzer außerdem aussagekräftigere Daten in einer Organisation, in dem Benutzer in der Regel nicht Windows am Ende des Tages abgemeldet werden. Stattdessen sie einfach ihre Computer sperren, und lassen Sie Windows und Skype für Unternehmen ausgeführt. In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich die Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben. Jedoch eindeutige aktive Benutzer erfahren Sie, ob der Benutzer aktiv Skype für Geschäftskunden und einem anderen Skype für Business Server-Client verwendet werden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können mit der Bericht über Benutzerregistrierung zum Anzeigen von Daten für alle Registrar-Pools und Edge-Server oder Daten für einen einzelnen Pool anzeigen. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.
  
**Filter im Bericht von Benutzer-Registrierung**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool oder **[Alle]** auswählen, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt. <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind. 
  
**Metriken im Bericht über der Benutzer-Registrierung**

|**Name**|**Können Sie nach dieser Metrik werden sortiert?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 07.07.2015 klicken, wird eine stündliche Übersicht der Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Anmeldungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der erfolgreichen Anmeldesitzungen.  <br/> |
|**Interne Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen im internen Netzwerk.  <br/> |
|**Externe Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen von außerhalb des internen Netzwerks über den Edgeserver.  <br/> |
|**Eindeutige angemeldete Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Anmeldesitzung hatten. Ein Benutzer, der mehrere Anmeldesitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Anmeldesitzung ausgeführt hat.  <br/> |
|**Eindeutige aktive Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die an einer Peer-to-Peer- oder Konferenzsitzung teilgenommen haben. Ein Benutzer, der mehrere Sitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Sitzung ausgeführt hat.  <br/> |
   

