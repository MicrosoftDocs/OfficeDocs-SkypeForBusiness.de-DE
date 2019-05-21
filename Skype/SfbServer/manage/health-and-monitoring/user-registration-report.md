---
title: Bericht zur Benutzerregistrierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Zusammenfassung: erfahren Sie mehr über den Bericht zur Benutzerregistrierung in Skype for Business Server.'
ms.openlocfilehash: efdb701a61f527e3dd56c1f1e0662f3f1b7f0f8b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279669"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Bericht zur Benutzerregistrierung in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Bericht zur Benutzerregistrierung in Skype for Business Server.
  
Der Bericht zur Benutzerregistrierung bietet eine Übersicht über die Benutzeranmelde Aktivitäten, insbesondere Informationen über die Anzahl der Benutzer, die sich während eines bestimmten Zeitraums bei Skype for Business Server angemeldet haben (stündlich, täglich, wöchentlich, monatlich). Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält. Er enthält keine Informationen dazu, welche Personen sich angemeldet haben. Überwachungsberichte liefern keine Informationen darüber, welche bestimmten Benutzer Skype for Business Server verwenden (und welche nicht). Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.
  
Bei der Bereitstellung von Informationen zu Benutzeranmeldungen macht der Bericht über Benutzerregistrierung zwei erhebliche Unterschiede. Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen. Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Firewall Ihres Unternehmens anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind). Externe Anmeldungen stellen Benutzer dar, die sich von außerhalb der Firewall über einen Edgeserver angemeldet haben (beispielsweise zählt ein Benutzer, der sich von einem Internet Café anmeldet, als externe Anmeldung). Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.
  
Der Bericht über Benutzerregistrierung enthält zudem Informationen darüber, wie viele aktive Benutzer in einem bestimmten Zeitraum anwesend waren. Ein aktiver Benutzer ist ein Benutzer, der an einer Chat-Sitzung teilgenommen, an einer Skype for Business Server-Besprechung teilgenommen, einen Telefonanruf getätigt oder empfangen oder in diesem Zeitraum anderweitig Skype for Business Server verwendet hat. Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht genutzt haben.
  
## <a name="accessing-the-user-registration-report"></a>Zugreifen auf den Bericht über Benutzerregistrierung

Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Optimale Nutzung des Berichts über Benutzerregistrierung

Nachdem Sie Skype for Business Server bereitgestellt haben, ist eine häufig gestellte Frage: Wie kann ich feststellen, ob meine Benutzer diese neue Technologie tatsächlich verwenden? Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung der Frage helfen. Wenn Sie feststellen möchten, ob Benutzer Skype for Business Server verwenden, müssen Sie zwei Dinge tun. Rufen Sie zunächst den Wert der Metrik „Eindeutige angemeldete Benutzer“ im Bericht über Benutzerregistrierung ab. Dieser Wert gibt an, wie viele verschiedene Personen bei Skype for Business Server angemeldet sind.
  
Im Vergleich dazu zeigt die Metrik "Gesamt Anmeldungen" an, wie viele Gesamtzeiten alle an Skype for Business Server angemeldet sind. Angenommen, Ken Myers hat an einem einzigen Tag fünf verschiedene Male bei Skype for Business Server angemeldet. In diesem Fall zählt Jan Sachweh als fünf separate Anmeldesitzungen in der Metrik „Anmeldungen insgesamt“, aber nur als ein angemeldeter Benutzer in der Metrik „Eindeutige angemeldete Benutzer“. Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an. So kann sich ein Benutzer beispielsweise mit seinem Desktopcomputer, seinem Laptop Computer, anmelden und über ein IP-Telefon verfügen, das sich automatisch bei Skype for Business Server anmeldet. In diesem Beispiel gibt es einen eindeutigen Benutzer mit drei Anmeldungen.
  
Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.
  
|**Benutzer**|**Anmeldezeitpunkt**|
|:-----|:-----|
|Ken Myer  <br/> |07.07.2015 08:45  <br/> |
|Ken Myer  <br/> |07.07.2015 08:46  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:17  <br/> |
|Ken Myer  <br/> |07.07.2015 09:22  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:31  <br/> |
   
Insgesamt fanden fünf Anmeldungen statt, es sind jedoch nur zwei eindeutige angemeldete Benutzer vorhanden: Ken Myer (der sich dreimal angemeldet hat) und Pilar Ackerman (die sich zweimal angemeldet hat). Darin besteht der Unterschied zwischen Anmeldungen und eindeutigen angemeldeten Benutzern.
  
Sie müssen nicht nur die Anzahl der eindeutigen Anmeldungen kennen, sondern auch die Gesamtzahl der Benutzer, die für Skype for Business Server aktiviert wurden. Dieser Wert kann abgerufen werden, indem Sie die Skype for Business Server-Verwaltungsshell öffnen und den folgenden Windows PowerShell-Befehl ausführen:
  
```
(Get-CsUser).Count
```

Wenn der vorhergehende Befehl einen Wert von 1.236 zurückgibt und der Wert der eindeutigen Anmeldebenutzer Metrik einen Mittelwert von 667 zurückgibt, deutet dies darauf hin, dass sich etwas mehr als die Hälfte der Benutzer für Skype for Business aktivieren, die sich tatsächlich täglich am System anmelden (das heißt , 667 dividiert durch 1.236, was etwa 54% beträgt.
  
> [!CAUTION]
> Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben. Bereits im System angemeldete Benutzer werden nicht erfasst. Wenn zum Beispiel die Metrik „Eindeutige angemeldete Benutzer“ 667 Anmeldungen anzeigt und insgesamt 1.236 Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer im System anmeldet. Nehmen wir jedoch an, 300 Benutzer waren bereits am System angemeldet, als Sie mit der Überprüfung der Anmeldedaten begonnen haben. Das würde bedeuten, dass Sie tatsächlich fast 1.000-Nutzer bei Skype for Business Server angemeldet haben, was bedeutet, dass Sie näher an 80% ihrer Nutzer angemeldet waren. 
  
Vergleichen Sie auch den Wert „Eindeutige angemeldete Benutzer“ mit dem Wert der Metrik „Eindeutige aktive Benutzer“. Die Metrik "eindeutige aktive Benutzer" gibt an, wie viele eindeutige Benutzer Skype for Business Server tatsächlich verwendet haben: Sie haben einen Anruf getätigt, haben sich einer Skype for Business Server-Besprechung angeschlossen, oder Sie haben an einer Chatsitzung teilgenommen. Dies sind nützliche Informationen, da Skype for Business Server so konfiguriert werden kann, dass jedes Mal, wenn ein Benutzer Windows startet, automatisch gestartet wird. Aus diesem Grund haben Sie möglicherweise eine große Anzahl von Benutzern, die sich automatisch bei Skype for Business anmelden, wenn Sie sich täglich bei Windows anmelden, den Skype for Business-Server in diesem Zeitraum aber niemals tatsächlich verwenden.
  
Die Metrik "eindeutige aktive Benutzer" bietet auch aussagekräftigere Daten in einer Organisation, in der Benutzer sich am Ende des Tages in der Regel nicht von Windows abmelden. Stattdessen Sperren Sie einfach Ihre Computer und lassen Windows und Skype for Business laufen. In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich die Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben. Bei eindeutigen aktiven Benutzern wird jedoch mitgeteilt, ob Benutzer Skype for Business oder einen anderen Skype for Business Server-Client aktiv verwenden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. So können Sie beispielsweise mit dem Bericht zur Benutzerregistrierung Daten für alle registrierungspools und-Edgeserver anzeigen oder Daten für einen einzelnen Pool anzeigen. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.
  
**Filter im Bericht über Benutzerregistrierung**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**Von** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 07.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 03.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall „Täglich“ mit dem Startdatum 07.07.2015 und dem Enddatum 28.02.2015 ausgewählt haben, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool oder **[Alle]** auswählen, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt. <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind. 
  
**Metriken im Bericht über Benutzerregistrierung**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 07.07.2015 klicken, wird eine stündliche Übersicht der Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Anmeldungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der erfolgreichen Anmeldesitzungen.  <br/> |
|**Interne Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen im internen Netzwerk.  <br/> |
|**Externe Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen von außerhalb des internen Netzwerks über den Edgeserver.  <br/> |
|**Eindeutige angemeldete Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Anmeldesitzung hatten. Ein Benutzer, der mehrere Anmeldesitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Anmeldesitzung ausgeführt hat.  <br/> |
|**Eindeutige aktive Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die an einer Peer-to-Peer- oder Konferenzsitzung teilgenommen haben. Ein Benutzer, der mehrere Sitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Sitzung ausgeführt hat.  <br/> |
   

