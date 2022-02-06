---
title: Benutzerregistrierungsbericht in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Zusammenfassung: Erfahren Sie mehr über den Benutzerregistrierungsbericht in Skype for Business Server.'
---

# <a name="user-registration-report-in-skype-for-business-server"></a>Benutzerregistrierungsbericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Benutzerregistrierungsbericht in Skype for Business Server.
  
Der Benutzerregistrierungsbericht enthält eine Übersicht über die Benutzeranmeldungsaktivitäten, insbesondere Informationen zur Anzahl der Benutzer, die sich während eines bestimmten Zeitraums bei Skype for Business Server angemeldet haben (stündlich, täglich, wöchentlich, monatlich). Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält. Er enthält keine Informationen dazu, welche Personen sich angemeldet haben. Überwachungsberichte enthalten keine Informationen darüber, welche bestimmten Benutzer Skype for Business Server verwenden (und welche nicht). Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.
  
Bei der Bereitstellung von Informationen zu Benutzeranmeldungen werden vom Bericht über Benutzerregistrierung zwei erhebliche Unterschiede hervorgehoben. Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen. Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Fierwall Ihrer Organisation anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind). Externe Anmeldungen stellen Benutzer dar, die sich von außerhalb der Firewall über einen Edgeserver angemeldet haben (z. B. zählt ein Benutzer, der sich über ein Internetcafé angemeldet hat, als externe Anmeldung). Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.
  
Der Bericht über Benutzerregistrierung enthält zudem Informationen darüber, wie viele aktive Benutzer in einem bestimmten Zeitraum anwesend waren. Ein aktiver Benutzer ist ein Benutzer, der an einer Chatsitzung teilgenommen, an einer Skype for Business Server Besprechung teilgenommen, einen Telefonanruf getätigt oder empfangen hat oder während dieses Zeitraums anderweitig Skype for Business Server verwendet hat. Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht tatsächlich genutzt haben.
  
## <a name="accessing-the-user-registration-report"></a>Zugreifen auf den Bericht über Benutzerregistrierung

Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Optimale Nutzung des Berichts über Benutzerregistrierung

Nachdem Sie Skype for Business Server ist eine häufig gestellte Frage folgende: Wie kann ich feststellen, ob meine Benutzer diese neue Technologie tatsächlich verwenden? Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung dieser Frage helfen. Um festzustellen, ob Benutzer Skype for Business Server verwenden, müssen Sie zwei Dinge tun. Rufen Sie zunächst den Wert der Metrik "Eindeutige angemeldete Benutzer" im Bericht über Benutzerregistrierung ab. Dieser Wert gibt an, wie viele unterschiedliche Personen sich bei Skype for Business Server angemeldet haben.
  
Im Vergleich dazu zeigt die Metrik Gesamtanzahl der Anmeldungen an, wie oft sich alle Benutzer bei Skype for Business Server angemeldet haben. Angenommen, Ken Myer hat sich an einem einzigen Tag fünf mal bei Skype for Business Server angemeldet. In diesem Fall zählt Ken Myer als fünf separate Anmeldesitzungen für die Metrik "Anmeldungen insgesamt", aber nur als ein angemeldeter Benutzer für die Metrik "Eindeutige angemeldete Benutzer". Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an. Beispielsweise kann sich ein Benutzer mit seinem Desktopcomputer, seinem Laptopcomputer anmelden und über ein IP-Telefon verfügen, das sich automatisch bei Skype for Business Server anmeldet. In diesem Beispiel ist ein eindeutiger Benutzer mit drei Anmeldungen vorhanden.
  
Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.
  
|**Benutzer**|**Anmeldezeitpunkt**|
|:-----|:-----|
|Ken Myer  <br/> |7.07.2015 08:45 Uhr  <br/> |
|Ken Myer  <br/> |7.07.2015 08:46 Uhr  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:17 Uhr  <br/> |
|Ken Myer  <br/> |7.07.2015 09:22 Uhr  <br/> |
|Pilar Ackerman  <br/> |07.07.2015 09:31 Uhr  <br/> |
   
Insgesamt fanden fünf Anmeldungen statt, es sind jedoch nur zwei eindeutige angemeldete Benutzer vorhanden: Ken Myer (der sich dreimal angemeldet hat) und Pilar Ackerman (die sich zweimal angemeldet hat). Darin besteht der Unterschied zwischen Anmeldungen und eindeutigen angemeldeten Benutzern.
  
Neben der Anzahl der eindeutigen Anmeldungen müssen Sie auch die Gesamtzahl der Benutzer kennen, die für Skype for Business Server aktiviert wurden. Dieser Wert kann durch Öffnen der Skype for Business Server Verwaltungsshell und Ausführen des folgenden befehls Windows PowerShell abgerufen werden:
  
```PowerShell
(Get-CsUser).Count
```

Wenn der vorherige Befehl den Wert 1.236 zurückgibt und die Metrik "Eindeutige Angemeldete Benutzer" einen Durchschnittswert von 667 zurückgibt, deutet dies darauf hin, dass sich etwas mehr als die Hälfte ihrer Benutzer für Skype for Business sich tatsächlich täglich am System anmelden (d. b. 667 geteilt durch 1.236, was ungefähr 54 % entspricht).
  
> [!CAUTION]
> Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben. Bereits am System angemeldete Benutzer werden nicht erfasst. Wenn die Metrik "Eindeutige angemeldete Benutzer" 667 Anmeldungen anzeigt und insgesamt 1.236 Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer am System anmeldet. Angenommen jedoch, 300 Benutzer waren bereits am System angemeldet, als Sie begonnen haben, die Anmeldedaten zu überprüfen. Dies würde bedeuten, dass fast 1.000 Benutzer bei Skype for Business Server angemeldet waren. Dies würde bedeuten, dass fast 80 % Ihrer Benutzer angemeldet waren. 
  
Vergleichen Sie auch den Wert "Eindeutige angemeldete Benutzer" mit dem Wert der Metrik "Eindeutige aktive Benutzer". Die Metrik "Eindeutige aktive Benutzer" gibt an, wie viele eindeutige Benutzer Skype for Business Server tatsächlich verwendet haben: sie haben einen Telefonanruf getätigt, an einer Skype for Business Server Besprechung teilgenommen oder an einer Chatsitzung teilgenommen. Dies sind nützliche Informationen, da Skype for Business Server so konfiguriert werden kann, dass sie jedes Mal automatisch gestartet wird, wenn ein Benutzer Windows startet. Aus diesem Grund haben Sie möglicherweise eine große Anzahl von Benutzern, die sich automatisch bei Skype for Business anmelden, wenn sie sich jeden Tag bei Windows anmelden, während dieses Zeitraums jedoch niemals tatsächlich Skype for Business Server verwenden.
  
Die Metrik "Eindeutige aktive Benutzer" bietet auch aussagekräftige daten in einer Organisation, in der sich Benutzer in der Regel nicht am Ende des Tages Windows abmelden. Stattdessen sperren sie einfach ihre Computer und lassen Windows und Skype for Business ausgeführt werden. In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben. Eindeutige aktive Benutzer sagen Ihnen jedoch, ob Benutzer aktiv Skype for Business oder einen anderen Skype for Business Server Client verwenden.
  
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Bericht über Benutzerregistrierung Daten für alle Registrierungsstellenpools und Edgeserver anzeigen oder Daten für einen einzelnen Pool anzeigen. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.
  
In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.
  
**Filter im Bericht über Benutzerregistrierung**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate können angezeigt werden) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie z. B. das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. s. Daten insgesamt 31 Tage). <br/> |
|**Pool** <br/> |Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool oder **[Alle]** auswählen, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt. <br/> |
   
## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind. 
  
**Metriken im Bericht über Benutzerregistrierung**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Stündlich** <br/> **Täglich** <br/> **Wöchentlich** <br/> **Monatlich** <br/> |Nein  <br/> |Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 7.07.2015 klicken, wird eine stündliche Aufschlüsselung der Benutzerregistrierungsaktivität für dieses Datum angezeigt.  <br/> |
|**Anmeldungen insgesamt** <br/> |Nein  <br/> |Die Gesamtzahl der erfolgreichen Anmeldesitzungen.  <br/> |
|**Interne Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen im internen Netzwerk.  <br/> |
|**Externe Anmeldungen** <br/> |Nein  <br/> |Die Gesamtzahl der Anmeldungen von außerhalb des internen Netzwerks über den Edgeserver.  <br/> |
|**Eindeutige angemeldete Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die mindestens eine Anmeldesitzung hatten. Ein Benutzer, der mehrere Anmeldesitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Anmeldesitzung ausgeführt hat.  <br/> |
|**Eindeutige aktive Benutzer** <br/> |Nein  <br/> |Die Gesamtzahl der Benutzer, die an einer Peer-zu-Peer- oder Konferenzsitzung teilgenommen haben. Ein Benutzer, der mehrere Sitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Sitzung ausgeführt hat.  <br/> |
   

