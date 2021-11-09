---
title: Konferenzaktivitätsbericht in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Zusammenfassung: Erfahren Sie mehr über den Konferenzaktivitätsbericht, der in Skype for Business Server verwendet wird.'
ms.openlocfilehash: c136bfaeb40a9b84c2861332636916353856855f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849928"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Konferenzaktivitätsbericht in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Konferenzaktivitätsbericht, der in Skype for Business Server verwendet wird.
  
Mit dem Konferenzaktivitätsbericht können Fragen wie diese leicht beantwortet werden: Wie viele Konferenzen werden täglich gehalten, und wann werden diese Konferenzen gehalten? Derartige Informationen sind an sich nützlich und können außerdem für die Problembehandlung verwendet werden. Nehmen wir z. B. an, dass sich Benutzer darüber beschweren, dass das Netzwerk mittags besonders langsam zu sein scheint. Ein kurzer Blick auf die Konferenzaktivitätsberichte könnte einen möglichen Grund vorschlagen: Viel mehr Konferenzen werden zwischen 10:00 Uhr und 14:00 Uhr geplant als zu jeder anderen Zeit.
  
Verursacht das langsame Netzwerk Probleme, können Sie Benutzern empfehlen, Konferenzen zu Tageszeiten mit weniger Datenauslastung abzuhalten.
  
## <a name="accessing-the-conference-activity-report"></a>Zugreifen auf den Konferenzaktivitätsbericht

Der Zugriff auf den Konferenzaktivitätsbericht erfolgt über den [Zusammenfassenden Konferenzbericht in Skype for Business Server,](conference-summary-report.md) indem Sie auf eine der folgenden Metriken klicken:
  
- Konferenzen insgesamt
    
- Teilnehmer insgesamt
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Optimales Verwenden des Konferenzaktivitätsberichts

Standardmäßig wird im Konferenzaktivitätsbericht die Gesamtanzahl der Konferenzen für den angegebenen Zeitraum (z. B. die Gesamtanzahl der Konferenzen pro Tag oder die Gesamtanzahl der Konferenzen pro Stunde eines Tages). Sie können jedoch auch die Gesamtanzahl der Teilnehmer für den Zeitraum oder die Gesamtanzahl der Teilnehmerminuten anzeigen. Klicken Sie dazu auf die Schaltfläche zum Ein- und Ausblenden der Parameter, um die Filteroptionen anzuzeigen, und wählen Sie dann eine der folgenden Optionen aus der Dropdownliste "Bericht nach" aus:
  
- Teilnehmeranzahl
    
- Teilnehmerminuten
    
- Konferenzanzahl
    
## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Konferenzaktivitätsbericht verwenden können.
  
**Filter im Konferenzaktivitätsbericht**

|**Name**|**Beschreibung**|
|:-----|:-----|
|**From** <br/> |Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Bis** <br/> |Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 7.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 7/7/2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 7/3/2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/> |
|**Intervall** <br/> | Zeitintervall. Wählen Sie eine der folgenden Optionen aus: <br/>  Stündlich (maximal 25 Stunden können angezeigt werden) <br/>  Täglich (maximal 31 Tage können angezeigt werden) <br/>  Wöchentlich (maximal 12 Wochen können angezeigt werden) <br/>  Monatlich (maximal 12 Monate werden angezeigt) <br/>  Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie z. B. das Intervall "Täglich" mit dem Startdatum 7.07.2015 und dem Enddatum 28.02.2015 auswählen, werden Daten für die Tage 07.08.2015 12:00 Uhr bis 07.09.2015 12:00 Uhr angezeigt (d. s. Daten insgesamt 31 Tage). <br/> |
|**Bericht nach:** <br/> | Gibt die Werte an, die in dem Bericht verwendet werden sollen. Sie können einen der folgenden Werte auswählen: <br/>  Teilnehmeranzahl <br/>  Teilnehmerminuten <br/>  Konferenzanzahl <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Metriken für Konferenzen nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Pool angegeben werden.
  
**Metriken für Konferenzen nach Pool**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Pool** <br/> |Nein  <br/> |Name des in der Konferenz verwendeten Registrierungspools oder Edgeservers.  <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.  <br/> |
|**Total** <br/> |Nein  <br/> |Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Metriken für Konferenzen nach Servertyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Servertyp angegeben werden.
  
**Metriken für Konferenzen nach Servertyp**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Konferenzservertyp** <br/> |Nein  <br/> | Der Typ des Servers, der in der Konferenz verwendet wird, in der Regel einer der folgenden: <br/>  Webkonferenzserver <br/>  Sofortnachrichten-Konferenzserver <br/>  Telefonkonferenzserver <br/>  A/V-Konferenzserver <br/>  Anwendungsfreigabe <br/> |
|**Datum/Uhrzeit** <br/> |Nein  <br/> |Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.  <br/> |
|**Total** <br/> |Nein  <br/> |Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.  <br/> |
   

