---
title: Bericht über Benutzerregistrierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Zusammenfassung: Erfahren Sie mehr über den Bericht über Benutzerregistrierung in Skype for Business Server.'
ms.openlocfilehash: cb732bdd10c051b35f4f2b69413168fd6515f998
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816645"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Bericht über Benutzerregistrierung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bericht über Benutzerregistrierung in Skype for Business Server.
  
Der Bericht über Benutzerregistrierung bietet eine Übersicht über die Benutzeranmeldeaktivität, insbesondere Informationen zur Anzahl der Benutzer, die sich während eines bestimmten Zeitraums (stündlich, täglich, wöchentlich, monatlich) bei Skype for Business Server angemeldet haben. Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält. Er enthält keine Informationen dazu, welche Personen sich angemeldet haben. Überwachungsberichte enthalten keine Informationen dazu, welche bestimmten Benutzer Skype for Business Server verwenden (und welche nicht). Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.
  
Bei der Bereitstellung von Informationen zu Benutzeranmeldungen werden vom Bericht über Benutzerregistrierung zwei erhebliche Unterschiede hervorgehoben. Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen. Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Fierwall Ihrer Organisation anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind). Externe Anmeldungen stellen Benutzer dar, die sich von außerhalb der Firewall über einen Edgeserver angemeldet haben (z. B. zählt ein Benutzer, der sich von einem Internetcafé aus angemeldet hat, als externe Anmeldung). Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.
  
Der Bericht über Benutzerregistrierung enthält zudem Informationen darüber, wie viele aktive Benutzer in einem bestimmten Zeitraum anwesend waren. Ein aktiver Benutzer ist ein Benutzer, der an einer Chatsitzung teilgenommen, an einer Skype for Business Server-Besprechung teilgenommen, einen Telefonanruf angenommen oder empfangen hat oder skype for Business Server in diesem Zeitraum anderweitig verwendet hat. Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht tatsächlich genutzt haben.
  
## <a name="accessing-the-user-registration-report"></a>Zugreifen auf den Bericht über Benutzerregistrierung

Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Optimale Nutzung des Berichts über Benutzerregistrierung

Nachdem Sie Skype for Business Server bereitgestellt haben, lautet eine häufig gestellte Frage: Wo finde ich informationen, ob meine Benutzer diese neue Technologie tatsächlich verwenden? Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung dieser Frage helfen. Um festzustellen, ob Benutzer Skype for Business Server verwenden, müssen Sie zwei Dinge tun. Rufen Sie zunächst den Wert der Metrik "Eindeutige angemeldete Benutzer" im Bericht über Benutzerregistrierung ab. Dieser Wert gibt an, wie viele unterschiedliche Personen sich bei Skype for Business Server angemeldet haben.
  
Im Vergleich dazu zeigt die Metrik "Anmeldungen insgesamt", wie oft sich alle Benutzer insgesamt bei Skype for Business Server angemeldet haben. Angenommen, Ken Myer hat sich fünf verschiedene Male an einem einzigen Tag bei Skype for Business Server angemeldet. In diesem Fall zählt Ken Myer als fünf separate Anmeldesitzungen für die Metrik "Anmeldungen insgesamt", aber nur als ein angemeldeter Benutzer für die Metrik "Eindeutige angemeldete Benutzer". Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an. Ein Benutzer kann sich beispielsweise mit seinem Desktopcomputer, seinem Laptopcomputer anmelden und über ein IP-Telefon verfügen, das sich automatisch bei Skype for Business Server anmeldet. In diesem Beispiel ist ein eindeutiger Benutzer mit drei Anmeldungen vorhanden.
  
Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.
  
|**Benutzer**|**Anmeldezeitpunkt**|
|:-----|:-----|
|Ken Myer  <br/> |07.07.2015 08:45  <br/> |
|Ken Myer  <br/> |07.07.2015 08:46  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:17  <br/> |
|Ken Myer  <br/> |07.07.2015 09:22  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:31  <br/> |
   
Insgesamt fanden fünf Anmeldungen statt, es sind jedoch nur zwei eindeutige angemeldete Benutzer vorhanden: Ken Myer (der sich dreimal angemeldet hat) und Pilar Ackerman (die sich zweimal angemeldet hat). Darin besteht der Unterschied zwischen Anmeldungen und eindeutigen angemeldeten Benutzern.
  
Sie müssen nicht nur die Anzahl der eindeutigen Anmeldungen kennen, sondern auch die Gesamtanzahl der Benutzer kennen, die für Skype for Business Server aktiviert wurden. Dieser Wert kann abgerufen werden, indem Sie die Skype for Business Server-Verwaltungsshell öffnen und den folgenden Windows PowerShell ausführen:
  
```PowerShell
(Get-CsUser).Count
```

Wenn der vorangehende Befehl den Wert 1.236 zurückgibt und die Metrik "Eindeutige Anmeldebenutzer" einen Durchschnittswert von 667 zurückgibt, deutet dies darauf hin, dass etwas mehr als die Hälfte der Für Skype for #A0 aktivierten Benutzer sich tatsächlich jeden Tag am System anmelden (d. h. 667 geteilt durch 1.236, also ca. 54 %).
  
> [!CAUTION]
> Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben. Bereits am System angemeldete Benutzer werden nicht erfasst. Wenn die Metrik "Eindeutige angemeldete Benutzer" 667 Anmeldungen anzeigt und insgesamt 1.236 Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer am System anmeldet. Angenommen jedoch, 300 Benutzer waren bereits am System angemeldet, als Sie begonnen haben, die Anmeldedaten zu überprüfen. Das würde bedeuten, dass sie tatsächlich fast 1.000 Benutzer bei Skype for Business Server angemeldet haben, was bedeutet, dass fast 80 % Ihrer Benutzer angemeldet sind. 
  
Vergleichen Sie auch den Wert "Eindeutige angemeldete Benutzer" mit dem Wert der Metrik "Eindeutige aktive Benutzer". Die Metrik "Eindeutige aktive Benutzer" gibt an, wie viele eindeutige Benutzer Tatsächlich Skype for Business Server verwendet haben: Sie haben einen Telefonanruf tätigt, an einer Skype for Business Server-Besprechung teilgenommen oder an einer Chatsitzung teilgenommen. Dies sind nützliche Informationen, da Skype for Business Server so konfiguriert werden kann, dass es bei jedem Start von Windows automatisch gestartet wird. Aus diesem Grund haben Sie möglicherweise eine große Anzahl von Benutzern, die sich automatisch bei Skype for Business anmelden, wenn sie sich täglich bei Windows anmelden, aber skype for Business Server in diesem Zeitraum nie tatsächlich verwenden.
  
Die Metrik "Eindeutige aktive Benutzer" bietet auch aussagekräftigere Daten in einer Organisation, in der sich Benutzer normalerweise nicht am Ende des Tages von Windows abmelden. Stattdessen sperren sie einfach ihre Computer und lassen Windows und Skype for Business weiter. In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben. Eindeutige aktive Benutzer teilt Ihnen jedoch mit, ob Benutzer Skype for Business oder einen anderen Skype for Business Server-Client aktiv verwenden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Bericht über Benutzerregistrierung Daten für alle Registrierungspools und Edgeserver oder für einen einzelnen Pool anzeigen. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.
  
**Filter im Bericht über Benutzerregistrierung**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 07.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Intervall "Täglich" mit dem Startdatum 7.7.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 00:00 Uhr bis 07.09.2015 00:00 Uhr angezeigt (d. h. Daten von insgesamt 31 Tagen). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool oder **[Alle]** auswählen, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt. <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind. 
  
**Metriken im Bericht über Benutzerregistrierung**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall "Täglich" verwenden und auf den 07.07.2015 klicken, wird eine stündlich aufschlüsselte Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Anmeldungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der erfolgreichen Anmeldesitzungen.  <br/> |
|**Interne Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen im internen Netzwerk.  <br/> |
|**Externe Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen von außerhalb des internen Netzwerks über den Edgeserver.  <br/> |
|**Eindeutige angemeldete Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Anmeldesitzung hatten. Ein Benutzer, der mehrere Anmeldesitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Anmeldesitzung ausgeführt hat.  <br/> |
|**Eindeutige aktive Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die an einer Peer-zu-Peer- oder Konferenzsitzung teilgenommen haben. Ein Benutzer, der mehrere Sitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Sitzung ausgeführt hat.  <br/> |
   

