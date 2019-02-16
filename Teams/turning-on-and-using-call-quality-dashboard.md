---
title: Aktivieren und Verwenden des Anrufqualitäts-Dashboards
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'See how to turn on and use the Skype for Business Online Call Quality Dashboard and get summary reports of quality of calls. '
ms.openlocfilehash: 18c5c87d437235733e9ffc7c8a1ec60883a33305
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069617"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="2c713-103">Einschalten und Aufrufen Qualitätsdashboard für Microsoft-Teams und Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="2c713-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="2c713-104">Hier erfahren Sie, wie Sie Ihre Office 365-Organisation konfigurieren können, um das Anrufqualitäts-Dashboard zur Überwachung der Anrufqualität zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c713-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="2c713-p101">Mit dem Anrufqualitäts-Dashboard (AQD) für Microsoft Teams und Skype for Business Online erhalten Sie einen Einblick in die Qualität von Anrufen, die mit Microsoft Teams- und Skype for Business-Diensten getätigt wurden. In diesem Thema werden die Schritte beschrieben, die Sie ausführen müssen, um die Datenerfassung zu starten.</span><span class="sxs-lookup"><span data-stu-id="2c713-p101">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c713-107">Die detaillierten CQD-Berichte sind derzeit als technische Vorschau für alle Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2c713-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="2c713-108">Aktuelle Änderungen und Updates</span><span class="sxs-lookup"><span data-stu-id="2c713-108">Latest changes and updates</span></span>

<span data-ttu-id="2c713-109">Dies sind die neuesten Änderungen am AQD:</span><span class="sxs-lookup"><span data-stu-id="2c713-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="2c713-110">Microsoft Teams-Daten sind zusätzlich zu Skype for Business Online-Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c713-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="2c713-111">Zusammenfassungsberichte enthalten einen Produktfilter, mit dem Sie alle Daten, Microsoft Teams-Daten oder Skype for Business Online-Daten auswählen können.</span><span class="sxs-lookup"><span data-stu-id="2c713-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="2c713-112">Video und VBSS Stream Qualität Klassifizierung Logik wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2c713-112">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="2c713-113">Die neuesten Klassifizierung Definitionen finden Sie unter [Stream-Klassifizierung Qualität Dashboards aufrufen](stream-classification-in-call-quality-dashboard.md) .</span><span class="sxs-lookup"><span data-stu-id="2c713-113">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="2c713-114">Finden Sie in diesem Artikel finden Sie eine Liste von [Dimensionen und Measures in Aufrufen Qualitätsdashboard zur Verfügung](dimensions-and-measures-available-in-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="2c713-114">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c713-115">Informationen zu Updates und Änderungen an das Dashboard finden Sie durch Klicken auf den Link in der **daran!**</span><span class="sxs-lookup"><span data-stu-id="2c713-115">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="2c713-116">Banner auf das Dashboard angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2c713-116">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="2c713-117">Aktivieren von Zusammenfassungsberichten des Microsoft-Anrufqualitäts-Dashboards (AQD)</span><span class="sxs-lookup"><span data-stu-id="2c713-117">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="2c713-118">Bevor Sie mit der Verwendung des AQD beginnen können, müssen Sie es für Ihre Office 365-Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2c713-118">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
 
<span data-ttu-id="2c713-119">![SFB-Logo-30x30.png](media/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="2c713-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="2c713-120">Melden Sie sich mit einem Administratorkonto bei Ihrer Office 365-Organisation an, und wählen Sie dann die Kachel **Admin** aus, um das Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2c713-120">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="2c713-121">Wählen Sie im linken Bereich unter **Admin Center** die Option **Skype for Business** aus, um das Skype for Business Admin Center zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2c713-121">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="2c713-122">Wählen Sie im linken Bereich des Skype for Business Admin Center die Option **Tools** aus, und wählen Sie dann **Qualitätsdashboard für Anrufe mit Skype for Business Online** aus.</span><span class="sxs-lookup"><span data-stu-id="2c713-122">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype for Business tools](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="2c713-124">Klicken Sie auf der Seite, die geöffnet wird, melden Sie sich mit Ihrem globale Administratorkonto ein, und geben Sie die Anmeldeinformationen für das Konto, wenn Sie aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="2c713-124">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![CQD Login](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="2c713-126">Nach der Anmeldung einmal aktiviert ist, beginnt die CQD sammeln und Verarbeitung von Daten.</span><span class="sxs-lookup"><span data-stu-id="2c713-126">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c713-127">Es kann einige Stunden dauern, bis genügend Daten verarbeitet worden sind, um in den Berichten aussagekräftige Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2c713-127">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a><span data-ttu-id="2c713-128">Funktionen des Anrufqualitäts-Dashboards für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2c713-128">Features of the Call Quality Dashboard for Skype for Business Online</span></span>
<span data-ttu-id="2c713-129"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="2c713-129"></span></span>

<span data-ttu-id="2c713-p104">CQD-Zusammenfassungsberichte bieten eine Reihe von Funktionen, die für detaillierte Berichte geplant sind. Die Unterschiede zwischen den zwei Versionen werden hier zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="2c713-p104">CQD Summary Reports provide a subset of the features planned for Detailed Reports. The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="2c713-132">**Funktion**</span><span class="sxs-lookup"><span data-stu-id="2c713-132">**Feature**</span></span>|<span data-ttu-id="2c713-133">**Zusammenfassungsberichte**</span><span class="sxs-lookup"><span data-stu-id="2c713-133">**Summary Reports**</span></span>|<span data-ttu-id="2c713-134">**Detaillierte Berichte**</span><span class="sxs-lookup"><span data-stu-id="2c713-134">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c713-135">Anwendungsfreigabemetrik</span><span class="sxs-lookup"><span data-stu-id="2c713-135">Application sharing metric</span></span>  <br/> |<span data-ttu-id="2c713-136">Nein</span><span class="sxs-lookup"><span data-stu-id="2c713-136">No</span></span>  <br/> |<span data-ttu-id="2c713-137">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-137">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-138">Unterstützung von Kunden-Gebäudeinformationen</span><span class="sxs-lookup"><span data-stu-id="2c713-138">Customer building information support</span></span>  <br/> |<span data-ttu-id="2c713-139">Ja </span><span class="sxs-lookup"><span data-stu-id="2c713-139">Yes</span></span>  <br/> |<span data-ttu-id="2c713-140">Ja </span><span class="sxs-lookup"><span data-stu-id="2c713-140">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-141">Drilldown-Analyse-Support</span><span class="sxs-lookup"><span data-stu-id="2c713-141">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="2c713-142">Nein</span><span class="sxs-lookup"><span data-stu-id="2c713-142">No</span></span>  <br/> |<span data-ttu-id="2c713-143">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-143">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-144">Medienzuverlässigkeitsmetriken</span><span class="sxs-lookup"><span data-stu-id="2c713-144">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="2c713-145">Nein</span><span class="sxs-lookup"><span data-stu-id="2c713-145">No</span></span>  <br/> |<span data-ttu-id="2c713-146">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-146">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-147">Sofort einsatzbereite Berichte</span><span class="sxs-lookup"><span data-stu-id="2c713-147">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="2c713-148">Ja </span><span class="sxs-lookup"><span data-stu-id="2c713-148">Yes</span></span>  <br/> |<span data-ttu-id="2c713-149">Ja </span><span class="sxs-lookup"><span data-stu-id="2c713-149">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-150">Übersichtsberichte</span><span class="sxs-lookup"><span data-stu-id="2c713-150">Overview reports</span></span>  <br/> |<span data-ttu-id="2c713-151">Ja </span><span class="sxs-lookup"><span data-stu-id="2c713-151">Yes</span></span>  <br/> |<span data-ttu-id="2c713-152">Ja </span><span class="sxs-lookup"><span data-stu-id="2c713-152">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-153">Berichtssatz pro Nutzer</span><span class="sxs-lookup"><span data-stu-id="2c713-153">Per-user report set</span></span>  <br/> |<span data-ttu-id="2c713-154">Nein</span><span class="sxs-lookup"><span data-stu-id="2c713-154">No</span></span>  <br/> |<span data-ttu-id="2c713-155">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-155">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-156">Anpassung des Berichtssatzes (Hinzufügen, Löschen, Ändern von Berichten)</span><span class="sxs-lookup"><span data-stu-id="2c713-156">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="2c713-157">Nein</span><span class="sxs-lookup"><span data-stu-id="2c713-157">No</span></span>  <br/> |<span data-ttu-id="2c713-158">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-158">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-159">Videobasierte Bildschirmfreigabe-Metriken</span><span class="sxs-lookup"><span data-stu-id="2c713-159">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="2c713-160">Nein</span><span class="sxs-lookup"><span data-stu-id="2c713-160">No</span></span>  <br/> |<span data-ttu-id="2c713-161">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-161">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-162">Videometriken</span><span class="sxs-lookup"><span data-stu-id="2c713-162">Video metrics</span></span>  <br/> |<span data-ttu-id="2c713-163">Nein</span><span class="sxs-lookup"><span data-stu-id="2c713-163">No</span></span>  <br/> |<span data-ttu-id="2c713-164">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-164">Yes</span></span>  <br/> |
|<span data-ttu-id="2c713-165">Verfügbare Datenmenge</span><span class="sxs-lookup"><span data-stu-id="2c713-165">Amount of data available</span></span>  <br/> |<span data-ttu-id="2c713-166">Letzte 6 Monate</span><span class="sxs-lookup"><span data-stu-id="2c713-166">Last 6 months</span></span>  <br/> |<span data-ttu-id="2c713-167">Letzte 6 Monate</span><span class="sxs-lookup"><span data-stu-id="2c713-167">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="2c713-168">Microsoft Teams-Daten</span><span class="sxs-lookup"><span data-stu-id="2c713-168">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="2c713-169">Ja</span><span class="sxs-lookup"><span data-stu-id="2c713-169">Yes</span></span>  <br/> |<span data-ttu-id="2c713-170">Ja </span><span class="sxs-lookup"><span data-stu-id="2c713-170">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="2c713-171">Sofort einsatzbereite Berichte</span><span class="sxs-lookup"><span data-stu-id="2c713-171">Out-of-the-box reports</span></span>

<span data-ttu-id="2c713-p105">Beide Versionen des AQD sind sofort einsatzbereit. So erhalten Sie Kennzahlen zur Anrufqualität, ohne neue Berichte erstellen zu müssen. Sobald Daten im Back-End verarbeitet wurden, können Sie die Daten zur Anrufqualität in den Berichten einsehen.</span><span class="sxs-lookup"><span data-stu-id="2c713-p105">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports. Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="2c713-174">Übersichtsberichte</span><span class="sxs-lookup"><span data-stu-id="2c713-174">Overview reports</span></span>

<span data-ttu-id="2c713-175">Beide Versionen von CQD bieten einen hervorragenden Einstiegspunkt in Bezug auf die Informationen zur allgemeinen Anrufqualität. Jedoch unterscheidet sich die Art der Darstellung der Informationen in den Zusammenfassungsberichten und den detaillierten Berichten.</span><span class="sxs-lookup"><span data-stu-id="2c713-175">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="2c713-176">Die Zusammenfassungsberichte bieten eine einfache Berichtsansicht mit Seiten im Registerformat, damit Benutzer den Bericht schneller durchsuchen und den Status sowie Trends bezüglich der allgemeinen Anrufqualität schneller nachvollziehen können.</span><span class="sxs-lookup"><span data-stu-id="2c713-176">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="2c713-177">Die vier Registerkarten umfassen:</span><span class="sxs-lookup"><span data-stu-id="2c713-177">The four tabs include:</span></span>
  
- <span data-ttu-id="2c713-178">**Gesamtanrufqualität** - Bietet Informationen zu allen Datenströmen. Hierbei handelt es sich um eine Aggregation der Server-Client-Datenströme und der Client-Client-Datenströme sowie um separate Server-Client- und Client-Client-Datenströme in Form monatlicher und täglicher Trends.</span><span class="sxs-lookup"><span data-stu-id="2c713-178">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="2c713-179">**Server - Client** - Bietet zusätzliche Details für die Datenströme zwischen Server- und Clientendpunkten.</span><span class="sxs-lookup"><span data-stu-id="2c713-179">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="2c713-180">**Client - Client** - Bietet zusätzliche Details für die Datenströme zwischen zwei Clientendpunkten.</span><span class="sxs-lookup"><span data-stu-id="2c713-180">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="2c713-181">**SLA zur Sprachqualität** - Bietet Informationen zu den Anrufen, die im SLA zur Sprachqualität für Skype for Business Online enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2c713-181">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="2c713-182">Registerkarte „Gesamtanrufqualität"</span><span class="sxs-lookup"><span data-stu-id="2c713-182">Overall Call Quality tab</span></span>

<span data-ttu-id="2c713-p106">Verwenden Sie die Daten auf dieser Registerkarte, um den Status und die Trends der Anrufqualität auszuwerten, indem Sie sich die Anzahl der Datenströme und die Prozentzahlen zu Anrufen mit schlechter Qualität ansehen. Die Legende oben rechts zeigt an, welche Farbe und welche visuellen Elemente diese Kennzahlen darstellen.</span><span class="sxs-lookup"><span data-stu-id="2c713-p106">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages. The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![CQD Data key](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="2c713-186">Streams are classified in three groups: Good, Poor, and Unclassified.</span><span class="sxs-lookup"><span data-stu-id="2c713-186">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="2c713-187">Es sind auch berechneten Werte *schlechter %* , mit denen Sie das Verhältnis von Datenströmen als *schlechte* der Anzahl insgesamt geschützte Stream klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="2c713-187">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="2c713-188">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span><span class="sxs-lookup"><span data-stu-id="2c713-188">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="2c713-189">Was für die Klassifizierung eines Stream-Objekts als schlecht oder eine gute verwendet wird finden Sie unter [Stream-Klassifizierung Qualität Dashboards aufrufen](stream-classification-in-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="2c713-189">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="2c713-190">Verwenden Sie die Skala auf der linken Seite, um den Datenstrom zählen von Werten zu messen.</span><span class="sxs-lookup"><span data-stu-id="2c713-190">Use the scale on the left to measure the stream count values.</span></span>
  
![CQD data count](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="2c713-192">Verwenden Sie die Skala rechts, um die Werte für „% Schlecht" zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2c713-192">Use the scale on the right to measure the Poor % values.</span></span>
  
![CQD data per cent](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="2c713-194">Sie erhalten auch die tatsächlichen numerischen Werte, indem Sie mit der Maus über eine Leiste fahren.</span><span class="sxs-lookup"><span data-stu-id="2c713-194">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c713-195">Das folgende Beispiel stammt aus einem kleinen Beispiel-Dataset, und die Werte sind für eine tatsächliche Bereitstellung nicht realistisch.</span><span class="sxs-lookup"><span data-stu-id="2c713-195">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![CQD Data numeric](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="2c713-197">Das gesamte Datenstromvolumen ist ein wichtiger Faktor bei der Bestimmung der Relevanz der berechneten Prozentsätze für die Klassifizierung „Schlecht".</span><span class="sxs-lookup"><span data-stu-id="2c713-197">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="2c713-198">Der kleinere der Lautstärke des allgemeinen Datenströme, die weniger zuverlässig sind die folgenden Werte gemeldeten schlechter Prozentsatz.</span><span class="sxs-lookup"><span data-stu-id="2c713-198">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="2c713-199">Registerkarten „Server-Client" und „Client-Client"</span><span class="sxs-lookup"><span data-stu-id="2c713-199">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="2c713-p109">Diese zwei Registerkarten bieten zusätzliche Details für die Datenströme, die in ihren entsprechenden Endpunkt-zu-Endpunkt-Szenarien aufgetreten sind. Beide Registerkarten haben vier reduzierbare Bereiche, die vier Szenarien darstellen, in denen die Medienströme sich bewegen würden.</span><span class="sxs-lookup"><span data-stu-id="2c713-p109">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios. Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="2c713-202">Innen verkabelt</span><span class="sxs-lookup"><span data-stu-id="2c713-202">Wired Inside</span></span>
    
- <span data-ttu-id="2c713-203">Außen verkabelt</span><span class="sxs-lookup"><span data-stu-id="2c713-203">Wired Outside</span></span>
    
- <span data-ttu-id="2c713-204">Innen WLAN</span><span class="sxs-lookup"><span data-stu-id="2c713-204">Wifi Inside</span></span>
    
- <span data-ttu-id="2c713-205">Außen WLAN</span><span class="sxs-lookup"><span data-stu-id="2c713-205">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="2c713-206">Innentest</span><span class="sxs-lookup"><span data-stu-id="2c713-206">Inside Test</span></span>

<span data-ttu-id="2c713-207">Bei der Verarbeitung klassifiziert das AQD-Back-End einen Datenstrom als  *Innen*  oder *Außen*  anhand von Gebäudeinformationen, falls diese vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2c713-207">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="2c713-208">Die Endpunkte jedes Datenstroms sind einer Subnetzadresse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2c713-208">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="2c713-209">Wenn das Subnetz in der Liste der Subnetze in der hochgeladenen Informationen zum Erstellen von InsideCorp gekennzeichnet ist, wird es *in*betrachtet.</span><span class="sxs-lookup"><span data-stu-id="2c713-209">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="2c713-210">Wenn erstellen Informationen nicht noch hochgeladen wurde, wird in Test immer die Datenströme als *externe*klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="2c713-210">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="2c713-211">Beachten Sie, dass beim Innentest für das Server-Client-Szenario nur der Clientendpunkt berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="2c713-211">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="2c713-212">Da sich Server aus der Perspektive des Benutzers stets außerhalb befinden, werden sie beim Test nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="2c713-212">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="2c713-213">Verkabelt oder WLAN</span><span class="sxs-lookup"><span data-stu-id="2c713-213">Wired vs. wifi</span></span>

<span data-ttu-id="2c713-p111">Wie es der Name bereits besagt, handelt es sich hier um das Klassifizierungskriterium basierend auf der Art der Clientverbindungen. Um es noch einmal zu verdeutlichen: Ein Server ist immer verkabelt und wird nicht in die Berechnung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="2c713-p111">As the names indicate, this is a classification criteria based on the type of client connections. Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c713-216">Wenn wir von einem Datenstrom ausgehen und einer der beiden Endpunkte mit einem WLAN verbunden ist, wird er im AQD als WLAN klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="2c713-216">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="2c713-217">Auswählen der Produktdaten, die in Berichten angezeigt werden sollen</span><span class="sxs-lookup"><span data-stu-id="2c713-217">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="2c713-218">In den Zusammenfassungsberichten und erweiterten Standortberichten können Sie mithilfe der Dropdownliste **Produktfilter** alle Produktdaten, nur Microsoft Teams-Daten oder nur Skype for Business Online-Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2c713-218">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![Screenshot shows the Product Filter control with options for All, Microsoft Teams, and Skype for Business.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="2c713-220">In ausführliche Berichte können Sie die Dimension **Teams ist** zum Filtern der Daten zu Microsoft-Teams oder Skype für Business Online-Daten als Teil der Definition des Berichts.</span><span class="sxs-lookup"><span data-stu-id="2c713-220">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-building-information"></a><span data-ttu-id="2c713-221">Hochladen von Gebäudeinformationen</span><span class="sxs-lookup"><span data-stu-id="2c713-221">Upload Building information</span></span>
<a name="BKMKBuildingInformationUpload"></a>

<span data-ttu-id="2c713-p112">Das Dashboard für AQD-Zusammenfassungsberichte enthält die Seite **Upload von Mandantendaten**, auf die Sie zugreifen können, indem Sie rechts oben im Einstellungsmenü die Option **Upload von Mandantendaten** auswählen. Diese Seite wird von Administratoren zum Hochladen ihrer eigenen Informationen verwendet, wie z. B. Zuordnung von IP-Adressen und geografischen Informationen, Zuordnung der einzelnen Funkzugriffspunkte und ihrer MAC-Adressen usw.</span><span class="sxs-lookup"><span data-stu-id="2c713-p112">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner. This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, etc.</span></span>
  
![CQD Dashboard](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="2c713-p113">Verwenden Sie das Dropdownmenü auf der Seite **Upload von Mandantendaten**, um einen Datendateityp für den Upload auszuwählen. Der Dateidatentyp bezeichnet den Inhalt der Datei (z. B. bezieht sich „Gebäude" auf die Zuordnung von IP-Adressen und Gebäuden sowie auf andere geografische Informationen). Derzeit unterstützen wir nur den Datentyp „Gebäude". Weitere Datentypen werden in den nächsten Versionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2c713-p113">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading. The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information). Currently we are only supporting the "Building" data type. A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="2c713-229">Klicken Sie nach Auswahl des Dateidatentyps auf **Durchsuchen**, um eine Datendatei auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2c713-229">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="2c713-230">Bei der Datendatei muss es sich um eine TSV-Datei (Datei mit tabulatorgetrennten Werten) oder eine CSV-Datei (Datei mit durch Trennzeichen getrennten Werten) handeln.</span><span class="sxs-lookup"><span data-stu-id="2c713-230">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="2c713-231">Wenn Sie eine CSV-Datei verwenden, wird jedes Feld, das ein Komma enthält müssen von Anführungszeichen umgeben sein oder Komma entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="2c713-231">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="2c713-232">Beispiel: Wenn Ihr Gebäudename NY,NY lautet, muss er in der CSV-Datei als „NY,NY" eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2c713-232">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="2c713-233">Die Datendatei darf maximal 50 MB groß sein.</span><span class="sxs-lookup"><span data-stu-id="2c713-233">The data file must be no larger than 50MB in size.</span></span>
    
   - <span data-ttu-id="2c713-234">Bei jeder Datendatei muss jede Spalte in der Datei einem vordefinierten Datentyp entsprechen, der später in diesem Thema besprochen wird.</span><span class="sxs-lookup"><span data-stu-id="2c713-234">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="2c713-235">Geben Sie nach Auswahl einer Datendatei das **Startdatum** und optional ein **Enddatum** ein.</span><span class="sxs-lookup"><span data-stu-id="2c713-235">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="2c713-236">Wählen Sie nach der Auswahl von **Startdatum** die Option **Hochladen** aus, um die Datei auf den AQD-Server hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="2c713-236">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="2c713-p115">Bevor die Datei hochgeladen wird, wird sie zunächst validiert. Sobald sie validiert ist, wird sie in einem Azure-BLOB gespeichert. Falls die Validierung fehlschlägt oder die Datei nicht in einem Azure-BLOB gespeichert werden kann, wird eine Fehlermeldung angezeigt, in der die Korrektur der Datei angefordert wird. Die folgende Abbildung zeigt einen Fehler, der auftritt, wenn die Anzahl der Spalten in der Datendatei falsch ist.</span><span class="sxs-lookup"><span data-stu-id="2c713-p115">Before the file is uploaded, it is first validated. Once validated, it is stored in an Azure blob. If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file. The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![CQD Example upload validation error](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="2c713-p116">Falls während der Validierung keine Fehler auftreten, war der Dateiupload erfolgreich. Sie können die hochgeladene Datendatei in der Tabelle **Meine Uploads** anzeigen. Dort wird eine vollständige Liste aller hochgeladenen Dateien für den aktuellen Mandanten unten auf der Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c713-p116">If no errors occur during validation, the file upload will succeed. You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="2c713-244">Jeder Datensatz zeigt eine hochgeladene Mandanten Datendatei mit Dateityp, zuletzt aktualisiert, Zeitraum, Beschreibung, eines Symbols entfernen und ein Symbol.</span><span class="sxs-lookup"><span data-stu-id="2c713-244">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="2c713-245">Um eine Datei zu entfernen, wählen Sie das Papierkorbsymbol in der Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="2c713-245">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="2c713-246">Um eine Datei herunterzuladen, wählen Sie das Downloadsymbol in der Spalte **Download** der Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="2c713-246">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![CQD My Uploads table](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a><span data-ttu-id="2c713-248">Dateiformat der Mandantendaten und Dateistruktur der Gebäudedaten</span><span class="sxs-lookup"><span data-stu-id="2c713-248">Tenant data file format and Building data file structure</span></span>
<span data-ttu-id="2c713-249"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="2c713-249"></span></span>

<span data-ttu-id="2c713-250">Das Format der Datei, die Sie hochladen, muss folgende Bedingungen erfüllen, um die Validierungsprüfung vor dem Hochladen zu bestehen.</span><span class="sxs-lookup"><span data-stu-id="2c713-250">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="2c713-251">Bei der Datei muss es sich um eine TSV-Datei (die Spalten in den einzelnen Zeilen werden durch Tabstopps getrennt) oder um eine CSV-Datei (alle Spalten werden durch Trennzeichen getrennt) handeln.</span><span class="sxs-lookup"><span data-stu-id="2c713-251">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="2c713-p118">Der Inhalt der Datendatei umfasst keine Tabellenüberschriften. Das bedeutet, dass die erste Zeile der Datendatei echte Daten enthalten muss, keine Überschriften wie „Netzwerk" usw.</span><span class="sxs-lookup"><span data-stu-id="2c713-p118">The content of the data file doesn't include table headers. That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="2c713-p119">In jeder Spalte kann der Datentyp nur eine Zeichenfolge, eine Zahl oder der boolesche Datentyp sein. Falls es eine Zahl ist, muss es sich um einen numerischen Wert handeln; falls es der boolesche Datentyp ist, muss der Wert entweder 0 oder 1 betragen.</span><span class="sxs-lookup"><span data-stu-id="2c713-p119">For each column, the data type can only be String, Number, or Bool. If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="2c713-256">Für jede Spalte ist der Datentyp String, die Daten können leer sein (aber dennoch durch eine entsprechende Trennzeichen (d. h., Registerkarte oder Komma) getrennt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2c713-256">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="2c713-257">Dadurch wird dem Feld eine leere Zeichenfolge zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2c713-257">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="2c713-258">14 Spalten für jede Zeile vorhanden sein muss, muss jeder Spalte die folgenden Daten Typ und die Spalten in der angegebenen Reihenfolge aus, in der folgenden Tabelle werden müssen:</span><span class="sxs-lookup"><span data-stu-id="2c713-258">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="2c713-259">**Spaltenname**</span><span class="sxs-lookup"><span data-stu-id="2c713-259">**Column Name**</span></span>|<span data-ttu-id="2c713-260">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="2c713-260">**Data type**</span></span>|<span data-ttu-id="2c713-261">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2c713-261">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c713-262">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="2c713-262">Network</span></span>  <br/> |<span data-ttu-id="2c713-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-263">String</span></span>  <br/> |<span data-ttu-id="2c713-264">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="2c713-264">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="2c713-265">Netzwerkname</span><span class="sxs-lookup"><span data-stu-id="2c713-265">NetworkName</span></span>  <br/> |<span data-ttu-id="2c713-266">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-266">String</span></span>  <br/> |<span data-ttu-id="2c713-267">USA/Seattle/SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="2c713-267">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="2c713-268">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="2c713-268">NetworkRange</span></span>  <br/> |<span data-ttu-id="2c713-269">Zahl</span><span class="sxs-lookup"><span data-stu-id="2c713-269">Number</span></span>  <br/> |<span data-ttu-id="2c713-270">26</span><span class="sxs-lookup"><span data-stu-id="2c713-270">26</span></span>  <br/> |
|<span data-ttu-id="2c713-271">BuildingName</span><span class="sxs-lookup"><span data-stu-id="2c713-271">BuildingName</span></span>  <br/> |<span data-ttu-id="2c713-272">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-272">String</span></span>  <br/> |<span data-ttu-id="2c713-273">SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="2c713-273">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="2c713-274">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="2c713-274">OwnershipType</span></span>  <br/> |<span data-ttu-id="2c713-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-275">String</span></span>  <br/> |<span data-ttu-id="2c713-276">Contoso</span><span class="sxs-lookup"><span data-stu-id="2c713-276">Contoso</span></span>  <br/> |
|<span data-ttu-id="2c713-277">BuildingType</span><span class="sxs-lookup"><span data-stu-id="2c713-277">BuildingType</span></span>  <br/> |<span data-ttu-id="2c713-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-278">String</span></span>  <br/> |<span data-ttu-id="2c713-279">IT Termination</span><span class="sxs-lookup"><span data-stu-id="2c713-279">IT Termination</span></span>  <br/> |
|<span data-ttu-id="2c713-280">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="2c713-280">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="2c713-281">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-281">String</span></span>  <br/> |<span data-ttu-id="2c713-282">Engineering</span><span class="sxs-lookup"><span data-stu-id="2c713-282">Engineering</span></span>  <br/> |
|<span data-ttu-id="2c713-283">Ort</span><span class="sxs-lookup"><span data-stu-id="2c713-283">City</span></span>  <br/> |<span data-ttu-id="2c713-284">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-284">String</span></span>  <br/> |<span data-ttu-id="2c713-285">Seattle</span><span class="sxs-lookup"><span data-stu-id="2c713-285">Seattle</span></span>  <br/> |
|<span data-ttu-id="2c713-286">ZipCode</span><span class="sxs-lookup"><span data-stu-id="2c713-286">ZipCode</span></span>  <br/> |<span data-ttu-id="2c713-287">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-287">String</span></span>  <br/> |<span data-ttu-id="2c713-288">98001</span><span class="sxs-lookup"><span data-stu-id="2c713-288">98001</span></span>  <br/> |
|<span data-ttu-id="2c713-289">Land</span><span class="sxs-lookup"><span data-stu-id="2c713-289">Country</span></span>  <br/> |<span data-ttu-id="2c713-290">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-290">String</span></span>  <br/> |<span data-ttu-id="2c713-291">USA</span><span class="sxs-lookup"><span data-stu-id="2c713-291">US</span></span>  <br/> |
|<span data-ttu-id="2c713-292">Bundesland</span><span class="sxs-lookup"><span data-stu-id="2c713-292">State</span></span>  <br/> |<span data-ttu-id="2c713-293">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-293">String</span></span>  <br/> |<span data-ttu-id="2c713-294">WA</span><span class="sxs-lookup"><span data-stu-id="2c713-294">WA</span></span>  <br/> |
|<span data-ttu-id="2c713-295">Region</span><span class="sxs-lookup"><span data-stu-id="2c713-295">Region</span></span>  <br/> |<span data-ttu-id="2c713-296">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2c713-296">String</span></span>  <br/> |<span data-ttu-id="2c713-297">MSUS</span><span class="sxs-lookup"><span data-stu-id="2c713-297">MSUS</span></span>  <br/> |
|<span data-ttu-id="2c713-298">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="2c713-298">InsideCorp</span></span>  <br/> |<span data-ttu-id="2c713-299">Bool</span><span class="sxs-lookup"><span data-stu-id="2c713-299">Bool</span></span>  <br/> |<span data-ttu-id="2c713-300">1</span><span class="sxs-lookup"><span data-stu-id="2c713-300">1</span></span>  <br/> |
|<span data-ttu-id="2c713-301">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="2c713-301">ExpressRoute</span></span>  <br/> |<span data-ttu-id="2c713-302">Bool</span><span class="sxs-lookup"><span data-stu-id="2c713-302">Bool</span></span>  <br/> |<span data-ttu-id="2c713-303">0</span><span class="sxs-lookup"><span data-stu-id="2c713-303">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="2c713-304">Der Netzwerkbereich kann zur Darstellung eines Supernetzes (einer Kombination aus mehreren Subnetzen mit einem einzelnen Routing-Präfix) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c713-304">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="2c713-305">Alle neuen Gebäude-Uploads werden auf sich überlappende Bereiche hin untersucht.</span><span class="sxs-lookup"><span data-stu-id="2c713-305">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="2c713-306">Wenn Sie zuvor eine Gebäudedatei hochgeladen haben, sollten Sie die aktuelle Datei herunterladen und erneut hochladen, um mögliche Überlappungen zu identifizieren und das Problem vor dem erneuten Hochladen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2c713-306">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="2c713-307">Alle Überlappungen in zuvor hochgeladenen Dateien können zu falschen Zuordnungen von Subnetzen zu Gebäuden in den Berichten führen.</span><span class="sxs-lookup"><span data-stu-id="2c713-307">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="2c713-308">Bestimmte VPN-Implementierungen meldet nicht genau die Subnetzinformationen.</span><span class="sxs-lookup"><span data-stu-id="2c713-308">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="2c713-309">Es wird empfohlen, beim Hinzufügen eines VPN-Subnetzes zur Gebäudedatei anstelle eines Eintrags für das Subnetz separate Einträge für jede Adresse im VPN-Subnetz als separates 32 Bit-Netzwerk hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2c713-309">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="2c713-310">Jede Zeile kann die gleichen Gebäudemetadaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c713-310">Each row can have the same building metadata.</span></span> <span data-ttu-id="2c713-311">Ein Beispiel: Anstelle einer Zeile für 172.16.18.0/24 sollten Sie 256 Zeilen verwenden - eine Zeile für jede Adresse zwischen 172.16.18.0/32 und 172.16.18.255/32 (einschließlich).</span><span class="sxs-lookup"><span data-stu-id="2c713-311">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 
  
## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="2c713-312">Auswählen eines Medientyps in detaillierten Berichten</span><span class="sxs-lookup"><span data-stu-id="2c713-312">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="2c713-313">Mit detaillierten Berichten können die Qualität und die Medienzuverlässigkeit von Medientypen für Audio, Video, Anwendungsfreigabe und videobasierte Bildschirmübertragung ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="2c713-313">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="2c713-314">Dimensionen und Measures Filter, die für einen einzelnen Medientyp spezifisch sind haben "Audio", "Video", "AppSharing" oder "VBSS" als Präfix.</span><span class="sxs-lookup"><span data-stu-id="2c713-314">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![Call Quality Dashboard Dimensions.](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="2c713-p123">Wenn Sie die Dimensionen und Kennzahlen für einen einzelnen Medientyp anzeigen möchten, müssen Sie möglicherweise die neue MediaType-Dimension sowie den neuen MediaType-Filter verwenden. Beispiel: Wenn ein Bericht die Gesamtzahl aller Sitzungen für verschiedene Medientypen enthalten soll, müssen Sie die MediaType-Dimension einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="2c713-p123">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required. For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![Call Quality Dashboard Total Stream Count.](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="2c713-319">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2c713-319">Related topics</span></span>
[<span data-ttu-id="2c713-320">Einrichten der Anrufanalyse von Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2c713-320">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="2c713-321">Verwenden Sie Analytics rufen Sie für die Problembehandlung bei schlechter Anrufqualität</span><span class="sxs-lookup"><span data-stu-id="2c713-321">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="2c713-322">Anrufanalyse- und Anrufqualitäts-Dashboard</span><span class="sxs-lookup"><span data-stu-id="2c713-322">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 