---
title: "Einrichten von Skype für BA aufrufen"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Einrichten und Analytics anrufen zu identifizieren und Problembehandlung bei Skype für Geschäfts- und Microsoft-Teams, Anruf Qualitätsprobleme verwenden."
ms.openlocfilehash: 287b45cf8363c03bf6b62cd68f8e2be681996101
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-skype-for-business-call-analytics"></a>Einrichten von Skype für BA aufrufen

Einen Skype für Business Online Admin können Analytics rufen Sie für die Problembehandlung bei Skype für Business und Microsoft-Teams, rufen Sie die Qualität und Verbindung Probleme. Es kann so richten Sie die folgenden Funktionen in Analytics rufen Sie ein hilfreich sein:
  
- Festlegen von Berechtigungen, die andere Mitarbeiter, wie etwa Helpdesk Agents können, verwenden Analytics aufrufen, aber verhindern, dass sie den Zugriff auf die restlichen der Skype für Business Administrationscenter. 
    
- Fügen Sie zum Erstellen von, Website und Mandanten Informationen durch Hochladen einer Datendatei TSV oder CSV Analytics aufrufen.
    
> [!NOTE]
> Die Anrufanalyse wird zurzeit als Vorschau bereitgestellt. Die hier beschriebenen Texte und Bilder entsprechen möglicherweise nicht dem, was Sie tatsächlich sehen. 
  
## <a name="set-call-analytics-permissions"></a>Festlegen von Berechtigungen Analytics aufrufen
<a name="BKMK_SetCAPerms"></a>

Als Administrator erhalten Sie Vollzugriff auf alle Funktionen von Analytics aufrufen. Darüber hinaus können Sie ein Helpdesk-Modell in Analytics anrufen verwenden, die Stufe 1 und Stufe 2 Berechtigungsgruppen enthält. Benutzer mit Berechtigungen der Stufe 1 können nur eine begrenzte Ansicht des Analytics aufrufen zugreifen. Benutzer mit Berechtigungen der Stufe 2 können den vollen Funktionsumfang von Anrufen Analytics zugreifen. Beide Berechtigungsstufen verhindern des Zugriffs auf den Rest der der Skype für Business Administrationscenter. Gewähren von Zugriff auf den Ebenen können Sie durch Hinzufügen einer Gruppe, die den Benutzer der Stufe 1 oder Seite Berechtigungen der Stufe 2 im Abschnitt enthält. Weitere Informationen hierzu finden Sie unter [gestuften Berechtigungen in Aufrufen Analytics einrichten](set-up-call-analytics.md#BKMK_SetUpTier).
  
Stufe 1 Helpdesk Agents behandeln Sie grundlegende Anrufqualität Probleme. Stufe 1 Agents untersuchen Sie Probleme bei Besprechungen nicht; Sammeln von Informationen, und klicken Sie dann auf einen Agent Stufe 2 ausweiten. Schicht 2-Agents finden Sie Informationen im detaillierten mithilfe von Anruflisten, die von Stufe 1 Agents ausgeblendet ist. Die folgende Tabelle bietet eine Übersicht über Informationen verfügbar Analytics Aufrufen von Agents.


|**Aktivität**|**Informationen in Anruf Analytics**|**Was sieht der Stufe 1-agent**|**Was sieht der Stufe 2-agent**|
|:-----|:-----|:-----|:-----|
|**Anrufe** <br/> |Name des Anrufers  <br/> |Nur der Name des Benutzers, auf denen der Agent gesucht.  <br/> |Name des Benutzers.  <br/> |
||Name des Empfängers  <br/> |Zeigt an, dass interne oder externe Benutzer.  <br/> |Name des Empfängers.  <br/> |
||Telefonnummer des Anrufers  <br/> |Gesamte Telefonnummer außer den letzten drei Ziffern mit Sternchen Symbole verborgen sind. Beispielsweise 15552823 ***.  <br/> |Gesamte Telefonnummer außer den letzten drei Ziffern mit Sternchen Symbole verborgen sind. Beispielsweise 15552823 ***.  <br/> |
||Telefonnummer des Empfängers  <br/> |Gesamte Telefonnummer außer den letzten drei Ziffern mit Sternchen Symbole verborgen sind. Beispielsweise 15552823 ***.  <br/> |Gesamte Telefonnummer außer den letzten drei Ziffern mit Sternchen Symbole verborgen sind. Beispielsweise 15552823 ***.  <br/> |
||**Rufen Sie Details** > Registerkarte**Erweitert** <br/> |Informationen nicht angezeigt.  <br/> |Alle Details dargestellt, wie etwa Gerätenamen, IP-Adresse, Subnetz Zuordnung und vieles mehr.  <br/> |
||**Rufen Sie Details** > **Erweitert** > Registerkarte**Debuggen** <br/> |Informationen nicht angezeigt.  <br/> |Alle Details dargestellt, wie DNS-Suffix und SSID.  <br/> |
|**Besprechungen** <br/> |Namen der Teilnehmer  <br/> |Nur der Name des Benutzers, auf denen der Agent gesucht. Andere Teilnehmer, die als interne oder externe Benutzer identifiziert.  <br/> |Alle Namen angezeigt.  <br/> |
||Teilnehmeranzahl  <br/> |Anzahl der Teilnehmer.  <br/> |Anzahl der Teilnehmer.  <br/> |
||Sitzungsdetails  <br/> |Sitzungsdetails mit Ausnahmen dargestellt. Nur der Name des Benutzers, auf denen der Agent gesucht wird angezeigt. Andere Teilnehmer, die als interne oder externe Benutzer identifiziert. Die letzten Sie drei Ziffern der Telefonnummer mit Sternchen Symbole verborgen.  <br/> |Sitzungsdetails dargestellt. Benutzernamen und Sitzungsdetails dargestellt. Die letzten Sie drei Ziffern der Telefonnummer mit Sternchen Symbole verborgen.  <br/> |
   
 **Einrichten von gestuften Berechtigungen in Aufrufen Analytics** 
 <a name="BKMK_SetUpTier"> </a>
  
1. Erstellen Sie Office 365-Sicherheitsgruppen für Ebene 1 und Ebene 2 zu, und fügen Sie die gewünschten Personen jeder Gruppe. Sie können auch vorhandene Sicherheitsgruppen wiederverwenden. Weitere Informationen finden Sie unter [erstellen, bearbeiten oder Löschen einer Sicherheitsgruppe in Office 365 Administrationscenter](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Wechseln Sie in das Office 365 Administrationscenter zu **Admin zentriert** > **Skype für Unternehmen**.
    
    > [!NOTE]
    > Wenn Sie in der alten Skype für Business Administrationscenter sorgt, wechseln Sie auf die neue Version durch Klicken auf **unser neues Administrationscenter versuchen stammen**. 
  
3. Die neue Skype für Business Administrationscenter klicken Sie auf **Berechtigungen**.
    
4. Fügen Sie die Office 365-Sicherheitsgruppen in die Felder **Stufe 1** und **Stufe 2** . Sie können mehrere Gruppen für jede Rolle hinzufügen.
    
     ![Screenshot zeigt die Berechtigungen für aufrufen Analytics-Seite mit den Optionen für Ebene 1 und Ebene 2-Berechtigungen.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Benutzer mit einem der folgenden Berechtigungsstufen erhalten Sie über die dedizierte URL *https://adminportal.services.skypeforbusiness.com*auf Analytics aufrufen.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Hochladen einer TSV oder CSV-Datei zum Hinzufügen, Erstellen von Website und Mandanten für Informationen
<a name="BKMK_UploadFiles"> </a>

Durch Hochladen einer CSV- oder TSV-Datei können Sie rufen Analytics erstellen, Website und Mandanten Informationen hinzufügen. Mit diesen Informationen können aufrufen Analytics physischen Standorten IP-Adressen zuordnen. Sie oder Helpdesk Agents sinnvoll, diese Informationen, die entsprechende Trends erkennen Anruf Probleme unterstützen. Angenommen, warum viele Benutzer im gleichen Gebäude müssen ähneln Qualitätsprobleme aufzurufen? 
  
![Screenshot zeigt die Seite Websites mit Werten für die Anzahl von Websites und die Anzahl der Subnetze und die Schaltfläche Wählen Sie Datei-Websitedaten durch Hochladen einer TSV oder einer CSV-Datei importieren.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Wenn Sie einen Skype für Business-Administrator sind, können Sie eine vorhandene Datendatei aus der Skype für Business Online aufrufen Qualitätsdashboard. Zuerst, laden Sie die Datei aus aufrufen Qualitätsdashboard, und klicken Sie dann Sie hochladen auf Analytics aufrufen. Um eine vorhandene Datendatei herunterzuladen, besuchen Sie die **Skype für Business Admin Center** > **Tools** > **Skype für Business Online aufrufen Qualitätsdashboard** > **jetzt hochladen**. Klicken Sie auf **Download** neben der gewünschten Datei, in der Liste **Meine Uploads** .
  
Wenn Sie die TSV oder CSV-Datei von Grund auf neu erstellen, finden Sie unter [Mandantendaten file Format und Erstellen von Daten-Dateistruktur](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Verwandte Themen
<a name="BKMK_UploadFiles"> </a>

[Verwendung aufrufen Analytics für die Problembehandlung bei schlechter Skype für Unternehmen die Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Was ist der Unterschied zwischen Analytics aufrufen, und rufen Sie Qualitätsdashboard?](difference-between-call-analytics-and-call-quality-dashboard.md)