---
title: Bericht zur Benutzeraktivität in Skype for Business Server 25
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
description: 'Zusammenfassung: erfahren Sie mehr über den Bericht zur Benutzeraktivität in Skype for Business Server.'
ms.openlocfilehash: 0fdb7ab84748e971da7ef50c2b63651511ee38c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817614"
---
# <a name="user-activity-report-in-skype-for-business-server"></a>Bericht zur Benutzeraktivität in Skype for Business Server

**Zusammenfassung:** Informieren Sie sich über den Bericht zur Benutzeraktivität in Skype for Business Server.

Der Bericht über Benutzeraktivität stellt eine detaillierte Liste der Peer-to-Peer- und Konferenzsitzungen bereit, die von Benutzern in einem bestimmten Zeitraum durchgeführt werden. Anders als bei vielen der Überwachungsberichte ist im Bericht über Benutzeraktivität jeder Anruf mit einzelnen Benutzern verknüpft. Für Peer-to-Peer-Sitzungen ist im Bericht beispielsweise der SIP-URI der Person angegeben, die den Anruf initiiert hat (der Absenderbenutzer), und der Person, die angerufen wurde (der Empfängerbenutzer). Wenn Sie die Informationen zu einer Konferenz erweitern, sehen Sie eine Liste aller Konferenzteilnehmer einschließlich der Rolle, die die bei dieser Konferenz hatten.

Der Bericht über Benutzeraktivität wird auch als „Helpdesk“-Bericht bezeichnet. Der Grund ist, dass der Bericht häufig vom Helpdesk-Personal verwendet wird, um Sitzungsinformationen für einen bestimmten Benutzer abzurufen. Sie können den Bericht nach Anrufen filtern, die von einem bestimmten Benutzer entgegengenommen oder initiiert wurden, indem Sie einfach den SIP-URI dieses Benutzers in das Feld „Präfix des Benutzer-URI“ eingeben.

Wenn Sie dies tun, gibt der Benutzer Aktivitätsbericht Informationen für jeden Benutzer zurück, dessen SIP-URI mit der angegebenen Zeichenfolge beginnt. Wenn Sie beispielsweise **Klaus** in das Feld für den URI eingeben, findet der Bericht über Benutzeraktivität **Klaus**.Buzov@litwareinc.com. Er findet aber auch die folgenden Benutzer:

- **Ken** Azi@litwareinc.com

- **Ken** Burg@litwareinc.com

- **Klaus**.Kiefer@litwareinc.com

- **Ken** Nedy@litwareinc.com

Wenn Sie sicherstellen möchten, dass Informationen nur für Ken Myers zurückgegeben werden, geben Sie entweder seinen vollständigen URI (Ken.Myer@litwareinc.com) in das Suchfeld oder zumindest den Typ des Ken-URIs ein, um ihn von anderen Benutzern in Ihrer Organisation eindeutig zu unterscheiden. Ein Beispiel:

Ken.my

## <a name="to-access-the-user-activity-report"></a>So greifen Sie auf den Bericht über Benutzeraktivität zu

Auf den Bericht über Benutzeraktivität können Sie von der Startseite für Überwachungsberichte aus zugreifen. Sie können auch den Benutzer Aktivitätsbericht erreichen, indem Sie auf die Benutzer-URI [-Metrik im IP Phone-Inventurbericht in Skype for Business Server](ip-phone-inventory-report.md)klicken. Wenn Sie im Bericht über Benutzeraktivität auf den Konferenz-URI (für eine Konferenz) klicken, gelangen Sie zum Konferenzdetailbericht. Wenn Sie auf die Detail Metrik eines Peer-to-Peer-Anrufs klicken, gelangen Sie auf ähnliche Weise [in den Bericht Peer-to-Peer-Sitzungsdetails in Skype for Business Server](peer-to-peer-session-detail-report.md).

## <a name="making-the-best-use-of-the-user-activity-report"></a>Optimales Verwenden des Berichts über Benutzeraktivität

Obwohl im Berichtbenutzer Aktivität viele gute Informationen vorhanden sind, können diese Informationen manchmal schwierig zu finden sein. So werden beispielsweise alle Benutzeraktivitäten, die während eines bestimmten Zeitraums in Ihrer Organisation stattfinden, in den Bericht zur Benutzeraktivität aufgenommen. Das bedeutet, dass im Bericht begraben Informationen darüber enthalten sind, welche Benutzer Skype for Business Server tatsächlich in irgendeiner Weise verwendet haben.

> [!NOTE]
> Technisch ist es möglich, dass einige Benutzeraktivitäten nicht aufgezeichnet werden: während Skype for Business Server versucht, Informationen zu allen Telefon anrufen zu speichern, ist es möglich, dass ein Anruf getätigt wurde, ohne dass die Informationen über diesen Anruf in die Datenbank. Skype for Business Server ist so konzipiert, dass es eine äußerst genaue, aber nicht unbedingt perfekte Darstellung der Verwendung von Skype for Business Server bietet. (Die Tatsache, dass es keine Garantie dafür gibt, dass 100% aller Anrufe aufgezeichnet werden, erklärt, warum die Skype for Business Server-Überwachung nicht als Abrechnungssystem verwendet werden sollte.) Zweitens: ein Überwachungsbericht kann höchstens 1.000-Datensätze anzeigen. Je nach Umfang der Benutzeraktivität und des Zeitraums, den Sie auswählen, werden bei der Abfrage möglicherweise nicht alle Daten zurückgegeben, die tatsächlich in der Datenbank gespeichert sind. 

- Welche Benutzter haben das System in diesem Zeitraum tatsächlich verwendet?

- Welcher der Benutzer war in diesem Zeitraum am aktivsten?

- Sind die Benutzer, die die meisten Telefonate durchführen, auch die Benutzer, die am häufigsten an Chatsitzungen teilnehmen?

Wenn Sie Antworten auf Fragen wie diese benötigen, können Sie die von den Überwachungsberichten abgerufenen Daten in ein Excel-Arbeitsblatt exportieren. Sie können dieses Arbeitsblatt und/oder eine CSV-Datei dann verwenden, um die Daten zu analysieren. Angenommen, Sie haben Berichtsdaten nach Excel und dann in eine CSV-Datei exportiert. Zu diesem Zeitpunkt können Sie die Daten aus dem Importieren. CSV-Datei in Windows PowerShell mithilfe eines Befehls ähnlich der folgenden:

```PowerShell
$x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"
```

Nachdem die Daten importiert wurden, können Sie mithilfe von einfachen Windows PowerShell-Befehlen Ihre Fragen beantworten. Mit dem folgenden Befehl wird beispielsweise eine Liste von eindeutigen Benutzern zurückgegeben, die in mindestens einer Sitzung als „Absenderbenutzer“ fungiert haben:

```PowerShell
$x | Group-Object "From user" | Select Name | Sort-Object Name
```

Anders ausgedrückt:

<pre>
Name
----
David.Ahs@litwareinc.com
Gilead.Amosnino@litwareinc.com
Henrik.Jensen@litwareinc.com
Ken.Myer@litwareinc.com
Pilar.Ackerman@litwareinc.com
</pre>

Mit diesem Befehl werden eindeutige Benutzer aufgelistet (basierend auf der Gesamtanzahl der Sitzungen, an denen sie teilgenommen haben:

```PowerShell
$x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Der Befehl gibt ähnliche Daten wie die folgenden zurück:

<pre>
Count    Name
-----    ----
  523    Ken.Myer@litwareinc.com
   63    David.Ahs@litwareinc.com
   29    Pilar.Ackerman@litwareinc.com
   17    Gilead.Amosnino@litwareinc.com
   10    Henrik.Jensen@litwareinc.com
</pre>

Dieser Befehl beschränkt die gemeldeten Sitzungen auf diejenigen mit Audio als Modalität ein:

```PowerShell
$x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending
```

Wenn Sie mit der Maus auf eine beliebige Diagnose-ID im Bericht zeigen, erscheint eine QuickInfo mit einer Beschreibung der ID.

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Benutzeraktivität können Sie beispielsweise die zurückgegebenen Daten nach Kriterien wie dem Aktivitätstyp (Peer-to-Peer-Sitzung oder Konferenzsitzung) oder nach der SIP-Adresse (zum Anzeigen der Aktivitäten eines Benutzers) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzeraktivität verwenden können.

**Bericht über Benutzeraktivität - Filter**


| **Name**                   | **Beschreibung**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|:---------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Von** <br/>             | Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 17.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 13.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/>                                                      |
| **Bis** <br/>               | Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:  <br/> 17.07.2015 13:00 Uhr  <br/> Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:  <br/> 17.07.2015  <br/> Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):  <br/> 13.07.2015  <br/> Eine Woche läuft immer von Sonntag bis einschließlich Samstag.  <br/>                                                             |
| **Aktivitätstyp** <br/>    | Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Peer-to-Peer <br/>  Konferenz <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Modalität** <br/>         | Die für Sie verfügbare Modalität ist je nach ausgewähltem Aktivitätstyp unterschiedlich. Wenn es sich bei dem Aktivitätstyp um Peer-to-Peer handelt, können Sie im auswählen. Dateiübertragung; Anwendungsfreigabe; Stimme oder Video als Modalität.  <br/> Wenn der Aktivitätstyp Konferenz ist, können Sie Chat-Telefonkonferenz, Webkonferenz, Anwendungsfreigabe, Sprach-/Videokonferenz oder Telefoniekonferenz auswählen.  <br/>                                                                                                                                                                                                                                            |
| **Sitzungskategorie** <br/> | Gibt an, ob die betreffende Aktivität erfolgreich war oder nicht. Wählen Sie eine der folgenden Optionen aus: <br/>  [Alle] <br/>  Erfolg <br/>  Erwarteter Fehler <br/>  Unerwarteter Fehler <br/>  Ein „erwarteter Fehler“ ist ein Fehler, der erwartungsgemäß auftritt. Hat beispielsweise ein Benutzer seinen Status auf „Nicht stören“ gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen. Ein „unerwarteter Fehler“ ist ein Fehler, der in einem ansonsten scheinbar fehlerfreien System auftritt. Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet. In diesem Fall würde der Fehler als „unerwartet“ gekennzeichnet. <br/> |
| **Präfix des Benutzer-URI** <br/>  | SIP-Adresse für den Benutzer. Um nur die Datensätze des Benutzers Ken Myer anzuzeigen, geben Sie die SIP-Adresse von Ken Myer ein, z. B.:  <br/> sip:kenmyer@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Peer-to-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.

**Metriken für Peer-to-Peer-Sitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Detail** <br/> |Nein  <br/> |Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Peer-to-Peer-Sitzungsbericht für die ausgewählte Sitzung an.  <br/> |
|**Absenderbenutzer** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Peer-to-Peer-Sitzung initiiert hat.  <br/> |
|**An Benutzer** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der der Peer-to-Peer-Sitzung beigetreten ist.  <br/> |
|**Modalitäten** <br/> |Ja  <br/> |In der Sitzung verwendete Kommunikationsart, z. B. Instant Messaging, Audio oder Dateiübertragung.  <br/> |
|**Einladungszeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Peer-to-Peer-Sitzungseinladung gesendet wurde.  <br/> |
|**Antwortzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der der eingeladene Benutzer die Sitzungseinladung annahm.  <br/> |
|**Endzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Peer-to-Peer-Sitzung endete.  <br/> |
|**Diagnose-ID** <br/> |Ja  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |

## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.

**Metriken für Konferenzsitzungen**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Konferenz-URI** <br/> |Ja  <br/> |Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Konferenzbericht für die ausgewählte Sitzung an. Erweitern Sie dieses Element, damit der der Bericht Informationen zu den Konferenzteilnehmern anzeigt. Ausführliche Informationen finden Sie im Abschnitt „Metriken für Konferenzteilnehmer“ weiter unten in diesem Thema.  <br/> |
|**Organisator** <br/> |Ja  <br/> |SIP-Adresse des Benutzers, der die Sitzung organisiert hat.  <br/> |
|**Pool** <br/> |Ja  <br/> |Name des in der Konferenz verwendeten Edgeservers (sofern vorhanden).  <br/> |
|**Startzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.  <br/> |
|**Endzeitpunkt** <br/> |Ja  <br/> |Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.  <br/> |

## <a name="metrics-for-conference-participants"></a>Metriken für Konferenzteilnehmer

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für jeden Teilnehmer einer Konferenz enthaltenen Informationen aufgeführt.

**Metriken für Konferenzteilnehmer**

|**Name**|**Kann nach dieser Metrik sortiert werden?**|**Beschreibung**|
|:-----|:-----|:-----|
|**Rolle** <br/> |Nein  <br/> |Konferenzrolle (z. B. Referent) des Benutzers.  <br/> |
|**Teilnehmer** <br/> |Nein  <br/> |SIP-Adresse des Benutzers  <br/> |
|**Verbindung** <br/> |Nein  <br/> |Art der Netzwerkverbindung, z. B. „From Internal“ für interne Verbindungen oder „From PSTN“ für Einwahlbenutzer.  <br/> |
|**Beitrittszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Benutzer der Konferenz beigetreten ist.  <br/> |
|**Beendigungszeitpunkt** <br/> |Nein  <br/> |Datum und Uhrzeit, an dem bzw. zu der der Benutzer die Konferenz verlassen hat.  <br/> |
|**Diagnose-ID** <br/> |Nein  <br/> |Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.  <br/> |


