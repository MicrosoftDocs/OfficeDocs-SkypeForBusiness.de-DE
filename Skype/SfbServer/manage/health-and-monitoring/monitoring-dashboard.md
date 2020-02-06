---
title: Verwenden des Überwachungs Dashboards in Skype for Business Server
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
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Zusammenfassung: erfahren Sie mehr über das Überwachungs Dashboard in Skype for Business Server.'
ms.openlocfilehash: c2c86d5d5ede9581a2b41f32594118ab2605d63a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817824"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="24094-103">Verwenden des Überwachungs Dashboards in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="24094-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="24094-104">**Zusammenfassung:** Informieren Sie sich über das Dashboard für die Überwachung in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="24094-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="24094-105">Das Überwachungs Dashboard bietet Administratoren einen schnellen Überblick über den Systemstatus und die Systemnutzung von Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="24094-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="24094-106">Im Dashboard wird eine Zusammenfassung wichtiger Systemmetriken für folgende Werte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="24094-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="24094-107">Gesamtwerte für den aktuellen Tag.</span><span class="sxs-lookup"><span data-stu-id="24094-107">Totals for the current day.</span></span> <span data-ttu-id="24094-108">Beachten Sie, dass die für den aktuellen Tag angezeigten Werte Daten repräsentieren, die von Mitternacht bis zum aktuellen Zeitpunkt aufgezeichnet wurden (basierend auf der Ortszeit des Berichtsservers).</span><span class="sxs-lookup"><span data-stu-id="24094-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="24094-109">Dies bedeutet, dass Sie in der Regel Daten für einen Teil des Tages und nicht für einen Zeitraum von 24 Stunden sehen.</span><span class="sxs-lookup"><span data-stu-id="24094-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="24094-110">Wenn beispielsweise die lokale Zeit des Servers 8:00 Uhr beträgt, werden die Daten im Wert von acht Stunden angezeigt, da zwischen Mitternacht und der aktuellen Uhrzeit von 8:00 Uhr acht Stunden vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="24094-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="24094-111">Gesamtwerte für die Woche sowie Trendgesamtwerte für die letzten sechs Wochen.</span><span class="sxs-lookup"><span data-stu-id="24094-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="24094-112">Gesamtwerte für den Monat sowie Trendgesamtwerte für die letzten sechs Monate (nur für die Systemauslastung).</span><span class="sxs-lookup"><span data-stu-id="24094-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="24094-113">Beachten Sie, dass Sie das Cmdlet " [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) " verwenden können, um die URL zurückzugeben, die für den Zugriff auf Skype for Business Server-Überwachungsberichte verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="24094-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="24094-114">Standardmäßig werden im Monitoring-Dashboard Daten für die folgenden Metriken für die aktuelle Woche angezeigt (und Trendgesamtwerte für die letzten sechs Wochen):</span><span class="sxs-lookup"><span data-stu-id="24094-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="24094-115">Metriken für die Systemauslastung</span><span class="sxs-lookup"><span data-stu-id="24094-115">System Usage Metrics</span></span>

 <span data-ttu-id="24094-116">**Registrierung**</span><span class="sxs-lookup"><span data-stu-id="24094-116">**Registration**</span></span>
  
- <span data-ttu-id="24094-117">Eindeutige Benutzeranmeldungen</span><span class="sxs-lookup"><span data-stu-id="24094-117">Unique user logons</span></span>
    
  <span data-ttu-id="24094-118">**Peer-to-Peer**</span><span class="sxs-lookup"><span data-stu-id="24094-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="24094-119">Sitzungen insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-119">Total sessions</span></span>
    
- <span data-ttu-id="24094-120">Chatsitzungen</span><span class="sxs-lookup"><span data-stu-id="24094-120">IM sessions</span></span>
    
- <span data-ttu-id="24094-121">Audiositzungen</span><span class="sxs-lookup"><span data-stu-id="24094-121">Audio sessions</span></span>
    
- <span data-ttu-id="24094-122">Videositzungen</span><span class="sxs-lookup"><span data-stu-id="24094-122">Video sessions</span></span>
    
- <span data-ttu-id="24094-123">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="24094-123">Application sharing</span></span>
    
- <span data-ttu-id="24094-124">Gesamtdauer der Audiositzungen in Minuten</span><span class="sxs-lookup"><span data-stu-id="24094-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="24094-125">Durchschn. Dauer der Audiositzungen in Minuten</span><span class="sxs-lookup"><span data-stu-id="24094-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="24094-126">**Konferenz**</span><span class="sxs-lookup"><span data-stu-id="24094-126">**Conference**</span></span>
  
- <span data-ttu-id="24094-127">Konferenzen insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-127">Total conferences</span></span>
    
- <span data-ttu-id="24094-128">Chatkonferenzen</span><span class="sxs-lookup"><span data-stu-id="24094-128">IM conferences</span></span>
    
- <span data-ttu-id="24094-129">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="24094-129">A/V conferences</span></span>
    
- <span data-ttu-id="24094-130">Anwendungsfreigabekonferenzen</span><span class="sxs-lookup"><span data-stu-id="24094-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="24094-131">Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="24094-131">Web conferences</span></span>
    
- <span data-ttu-id="24094-132">Organisatoren insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-132">Total organizers</span></span>
    
- <span data-ttu-id="24094-133">Gesamtdauer der A/V-Konferenzen in Minuten</span><span class="sxs-lookup"><span data-stu-id="24094-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="24094-134">Durchschn. Dauer der A/V-Konferenzen in Minuten</span><span class="sxs-lookup"><span data-stu-id="24094-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="24094-135">PSTN-Konferenzen insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="24094-136">PSTN-Teilnehmer insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="24094-137">PSTN-Teilnehmerminuten insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="24094-138">Neben den Metriken für die Systemauslastung werden für die folgenden Metriken Gesamtwerte für den aktuellen Tag und die letzten sechs Tage (wenn Sie **Wöchentliche Ansicht** auswählen) bzw. für die aktuelle Woche und die letzten sechs Wochen (wenn Sie **Monatliche Ansicht** auswählen) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24094-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="24094-139">Anrufdiagnose pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="24094-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="24094-140">**Benutzer mit Anruffehlern**</span><span class="sxs-lookup"><span data-stu-id="24094-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="24094-141">Benutzer insgesamt mit Anruffehlern</span><span class="sxs-lookup"><span data-stu-id="24094-141">Total users with call failures</span></span>
    
- <span data-ttu-id="24094-142">Konferenzorganisatoren mit Anruffehlern</span><span class="sxs-lookup"><span data-stu-id="24094-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="24094-143">**Benutzer mit Anrufen schlechter Qualität**</span><span class="sxs-lookup"><span data-stu-id="24094-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="24094-144">Benutzer insgesamt mit Anrufen schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="24094-145">Anrufdiagnose</span><span class="sxs-lookup"><span data-stu-id="24094-145">Call Diagnostics</span></span>

<span data-ttu-id="24094-146">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="24094-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="24094-147">Fehler insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-147">Total failures</span></span>
    
- <span data-ttu-id="24094-148">Fehlerrate insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-148">Overall failure rate</span></span>
    
- <span data-ttu-id="24094-149">Chatfehlerrate</span><span class="sxs-lookup"><span data-stu-id="24094-149">IM failure rate</span></span>
    
- <span data-ttu-id="24094-150">Audio-Fehlerrate</span><span class="sxs-lookup"><span data-stu-id="24094-150">Audio failure rate</span></span>
    
- <span data-ttu-id="24094-151">Anwendungsfreigabe-Fehlerrate</span><span class="sxs-lookup"><span data-stu-id="24094-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="24094-152">Konferenz</span><span class="sxs-lookup"><span data-stu-id="24094-152">Conference</span></span>
  
- <span data-ttu-id="24094-153">Fehler insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-153">Total failures</span></span>
    
- <span data-ttu-id="24094-154">Fehlerrate insgesamt</span><span class="sxs-lookup"><span data-stu-id="24094-154">Overall failure rate</span></span>
    
- <span data-ttu-id="24094-155">Chatfehlerrate</span><span class="sxs-lookup"><span data-stu-id="24094-155">IM failure rate</span></span>
    
- <span data-ttu-id="24094-156">A/V-Fehlerrate</span><span class="sxs-lookup"><span data-stu-id="24094-156">A/V failure rate</span></span>
    
- <span data-ttu-id="24094-157">Anwendungsfreigabe-Fehlerrate</span><span class="sxs-lookup"><span data-stu-id="24094-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="24094-158">Fünf Server mit den meisten fehlerhaften Sitzungen</span><span class="sxs-lookup"><span data-stu-id="24094-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="24094-159">Medienqualitätsdiagnose</span><span class="sxs-lookup"><span data-stu-id="24094-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="24094-160">Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="24094-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="24094-161">Gesamtzahl der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="24094-162">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="24094-163">PSTN-Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="24094-164">Konferenz</span><span class="sxs-lookup"><span data-stu-id="24094-164">Conference</span></span>
  
- <span data-ttu-id="24094-165">Gesamtzahl der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="24094-166">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="24094-167">PSTN-Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="24094-168">Server mit dem höchsten Prozentsatz von Anrufen schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="24094-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="24094-169">Arbeiten mit dem Monitoring-Dashboard</span><span class="sxs-lookup"><span data-stu-id="24094-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="24094-p103">Wie bereits erwähnt, werden standardmäßig Gesamtwerte für die aktuelle Woche sowie Trendwerte für die letzten sechs Wochen angezeigt. Wenn Sie Gesamtwerte für den aktuellen Monat (sowie Trendwerte für die letzten sechs Monate) vorziehen, klicken Sie in der oberen rechten Ecke des Dashboards auf den Link **Monatliche Ansicht**. Wenn Sie monatliche Gesamtwerte anzeigen, wird der Text des Links in **Wöchentliche Ansicht** geändert. Durch Klicken auf diesen Link wechseln Sie wieder zur wöchentlichen Ansicht.</span><span class="sxs-lookup"><span data-stu-id="24094-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="24094-p104">Im Monitoring-Dashboard werden Gesamtwerte für die aktuelle Woche (oder den aktuellen Monat) sowie Trendwerte für die letzten sechs Wochen (oder Monate) angezeigt. Diese Zeiträume können nicht geändert werden. Beispielsweise können Sie mit dem Dashboard keine Berichtgesamtwerte für die letzten neun Monate anzeigen.</span><span class="sxs-lookup"><span data-stu-id="24094-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="24094-p105">Mit den Werten in den Spalten **Diese Woche**, **Dieser Monat** oder **Heute** sind jeweils ausführlichere Informationen verknüpft. Bedenken Sie, dass der Spaltenname und die darin angezeigten Werte oft voneinander abweichen, je nachdem, welche Metrik Sie auswählen und ob Sie die wöchentliche Ansicht oder die monatliche Ansicht ausgewählt haben. Wenn Sie z. B. auf die angezeigten Gesamtwerte für die Metrik **Eindeutige Benutzeranmeldungen** klicken, wird der **Bericht über Benutzerregistrierung** für den angegebenen Zeitraum angezeigt. Durch Klicken auf **Dashboard** können Sie jederzeit wieder zum Monitoring-Dashboard wechseln.</span><span class="sxs-lookup"><span data-stu-id="24094-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="24094-181">Sie können auch auf die Startseite der Monitoring Server-Berichte zugreifen, indem Sie in der oberen rechten Ecke des Dashboards auf den Link **Berichte** klicken.</span><span class="sxs-lookup"><span data-stu-id="24094-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="24094-p106">In der Spalte **Trend** wird ein einfaches Liniendiagramm mit den Gesamtwerten für die letzten sechs Wochen (oder in Abhängigkeit von der Metrik und dem Zeitintervall für die letzten sechs Tage oder die letzten sechs Monate) angezeigt. Diese einfachen Liniendiagramme enthalten einen unbeschrifteten Datenpunkt für jeden Zeitraum (z. B. einen unbeschrifteten Datenpunkt für jede der letzten sechs Wochen). Sie können jedoch tatsächliche Werte für diese Diagramme abrufen, indem Sie mit dem Mauszeiger über das Diagramm fahren. Es wird daraufhin eine QuickInfo mit den maximalen und minimalen Werten im Diagramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24094-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="24094-186">Exportieren von Daten aus dem Monitoring-Dashboard</span><span class="sxs-lookup"><span data-stu-id="24094-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="24094-p107">Im Monitoring-Dashboard gibt es eine Reihe von Möglichkeiten zum Exportieren der aktuellen Dashboardansicht. In der Symbolleiste des Dashboards wird ein Symbol für eine Diskette mit einem grünen Pfeil angezeigt. Durch Klicken auf dieses Symbol wird eine Dropdownliste mit den folgenden Datenexportformaten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="24094-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="24094-190">XML-Datei mit Berichtsdaten</span><span class="sxs-lookup"><span data-stu-id="24094-190">XML file with report data</span></span>
    
- <span data-ttu-id="24094-191">CSV (Komma als Trennzeichen)</span><span class="sxs-lookup"><span data-stu-id="24094-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="24094-192">PDF</span><span class="sxs-lookup"><span data-stu-id="24094-192">PDF</span></span>
    
- <span data-ttu-id="24094-193">MHTML (Webarchiv)</span><span class="sxs-lookup"><span data-stu-id="24094-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="24094-194">Excel</span><span class="sxs-lookup"><span data-stu-id="24094-194">Excel</span></span>
    
- <span data-ttu-id="24094-195">TIFF-Datei</span><span class="sxs-lookup"><span data-stu-id="24094-195">TIFF file</span></span>
    
- <span data-ttu-id="24094-196">Word</span><span class="sxs-lookup"><span data-stu-id="24094-196">Word</span></span>
    
<span data-ttu-id="24094-197">Zum Exportieren der aktuellen Dashboardansicht (und der zugehörigen Werte), klicken Sie auf die gewünschte Exportoption.</span><span class="sxs-lookup"><span data-stu-id="24094-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="24094-198">Skype for Business Server generiert einen Bericht im angegebenen Format und gibt Ihnen dann die Möglichkeit, diesen Bericht zu öffnen oder zu speichern.</span><span class="sxs-lookup"><span data-stu-id="24094-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="24094-199">Beachten Sie, dass Skype for Business Server standardmäßig das Dashboard für die Berichts **Überwachung** ausgibt und es in Ihrem Ordner "Downloads" speichert.</span><span class="sxs-lookup"><span data-stu-id="24094-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="24094-200">Wenn Sie den Bericht anders benennen oder in einem anderen Ordner speichern möchten, klicken Sie auf den Pfeil neben der Schaltfläche **Speichern** und klicken Sie dann auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="24094-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="24094-201">Wenn Sie den Namen **Monitoring-Dashboard** übernehmen und den Bericht im Ordner „Downloads“ speichern möchten, können Sie einfach auf die Schaltfläche **Speichern** klicken.</span><span class="sxs-lookup"><span data-stu-id="24094-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="24094-p109">Beim Exportieren von Dashboarddaten wird möglicherweise ein **Sicherheitshinweis** angezeigt, dass Ihre aktuellen Einstellungen das Herunterladen dieser Datei nicht zulassen. Führen Sie in diesem Fall die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="24094-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="24094-204">Wählen Sie in Internet Explorer die Option **Internetoptionen** aus.</span><span class="sxs-lookup"><span data-stu-id="24094-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="24094-205">Klicken Sie im Dialogfeld **Internetoptionen** auf der Registerkarte **Sicherheit** auf **Vertrauenswürdige Sites** und dann auf **Sites**.</span><span class="sxs-lookup"><span data-stu-id="24094-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="24094-206">Klicken Sie im Dialogfeld **vertrauenswürdige Websites** auf **Hinzufügen** , um den Skype for Business-Server, auf dem Skype for Business Server-Berichte ausgeführt werden, den Sammlungen vertrauenswürdiger Websites hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="24094-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="24094-207">Klicken Sie auf **Schließen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="24094-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="24094-p110">Anschließend müssen Sie das Monitoring-Dashboard aktualisieren, damit die Änderungen wirksam werden. Drücken Sie dazu entweder F5 oder klicken in der Symbolleiste des Dashboards auf das Symbol **Aktualisieren**. (Das Symbol **Aktualisieren** ist ein Kreis, in dem sich ein grünes Pfeilpaar befindet.)</span><span class="sxs-lookup"><span data-stu-id="24094-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="24094-p111">Sie können auch ein Excel-Arbeitsblatt mit Livedatenfeeds erstellen, das Links zu den neuesten Monitoring-Dashboard-Daten enthält. Zum Erstellen einer Livedatenfeed-Datei klicken Sie in der Symbolleiste auf das orangefarbene Symbol **In Datenfeed exportieren**.</span><span class="sxs-lookup"><span data-stu-id="24094-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="24094-213">Wenn Sie das aktuelle Dashboard drucken möchten, klicken Sie in der Symbolleiste auf das Druckersymbol.</span><span class="sxs-lookup"><span data-stu-id="24094-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

