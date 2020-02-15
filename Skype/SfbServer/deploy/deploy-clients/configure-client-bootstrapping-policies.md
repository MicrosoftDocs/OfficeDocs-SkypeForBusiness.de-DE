---
title: Konfigurieren von clientbootstrapping-Richtlinien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Gruppenrichtlinien verwalten.'
ms.openlocfilehash: 4db9becc32e8f9bca99f06ac4533d33e82666591
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029056"
---
# <a name="configure-client-bootstrapping-policies"></a>Konfigurieren von clientbootstrapping-Richtlinien
 
**Zusammenfassung:** Verwalten von Gruppenrichtlinien
  
Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools, die Sie zum Verwalten von Gruppenrichtlinien verwenden. Zur administrativen Vorlage für die Office-Gruppenrichtlinie gehören lync16. ADMX (ADMX) und. ADML (ADML) administrative Vorlagen, die die registrierungsbasierten Richtlinieneinstellungen für Skype for Business enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. ADML-Dateien sind sprachspezifische Ergänzungen zu ADMX-Dateien. Jede ADMX-und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung. Sie können [die Office 2016 administrativen Vorlagendateien (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) kostenlos aus dem Microsoft Download Center herunterladen.
  
Für Skype for Business-Clients gibt es mehrere clientbootstrapping-Richtlinien, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden. Beispielsweise die Standardserver und der Sicherheitsmodus, die der Client verwenden soll, bis die Anmeldung abgeschlossen ist. Sie können Gruppenrichtlinien verwenden, um diese Einstellungen in den Computer Registrierungen der Benutzer einzurichten, bevor Sie sich anmelden und mit dem Empfang von in-Band-prokonfigurations Einstellungen vom Server beginnen. In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für Skype for Business verfügbar sind.
  
**Gruppenrichtlinieneinstellungen für Skype for Business**

|Gruppenrichtlinieneinstellung|Beschreibung|
|:-----|:-----|
|Server angeben (ConfigurationMode)  <br/> | Gibt an, wie Skype for Business den Transport und den Server identifiziert, der während der Anmeldung verwendet werden soll. In dieser Einstellung geben Sie Folgendes an: <br/>  ServerAddressExternal: gibt den Servernamen oder die IP-Adresse an, die von Clients und verbundkontakten beim Herstellen einer Verbindung von außerhalb der externen Firewall verwendet wird. <br/>  ServerAddressInternal: gibt den Servernamen oder die IP-Adresse an, die verwendet wird, wenn Clients innerhalb der Firewall der Organisation eine Verbindung herstellen. <br/>  Transport: gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an. <br/> |
|Unterstützte zusätzliche Server Versionen (ConfiguredServerCheckValues)  <br/> |Gibt eine Liste von Server Versionsnamen an, die durch Semikolons getrennt sind, an denen Skype for Business Server sich anmeldet, zusätzlich zu den standardmäßig unterstützten Server Versionen.  <br/> |
|Deaktivieren des automatischen Uploads von Anmeldefehler Protokollen (DisableAutomaticSendTracing)  <br/> |Lädt die Anmeldefehler Protokolle automatisch in Skype for Business Server zur Analyse hoch. Wenn die Anmeldung erfolgreich verläuft, werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:  <br/> Für Skype for Business Online Benutzer: Anmeldefehler Protokolle werden automatisch hochgeladen. Für Skype for Business lokale Benutzer: ein Bestätigungsdialogfeld wird dem Benutzer vor dem Hochladen angezeigt. Wenn diese Einstellung deaktiviert ist, werden Anmelde Protokolle automatisch in den Skype for Business Server für Skype for Business lokale und Skype for Business Online Benutzer hochgeladen. Wenn diese Einstellung aktiviert ist, werden Anmelde Protokolle nie automatisch hochgeladen.  <br/> |
|HTTP-Fallback für SIP-Verbindung deaktivieren (DisableHttpConnect)  <br/> |Verhindert, dass Skype for Business Server versucht, eine Verbindung mit dem Server über HTTP herzustellen, wenn TLS oder TCP nicht verfügbar sind. Standardmäßig versucht Skype for Business zunächst, eine Verbindung mit dem Server mithilfe von TLS oder TCP herzustellen, und Skype for Business versucht, eine Verbindung über HTTP herzustellen, wenn keine dieser Transportmethoden erfolgreich ist. Verwenden Sie diese Richtlinie, um die Fallbackoption für den HTTP-Verbindungsversuch zu deaktivieren.  <br/> |
|Anmeldeinformationen erforderlich (DisableNTCredentials)  <br/> |Erfordert, dass der Benutzeranmeldeinformationen für Skype for Business bereitstellt, anstatt bei der Anmeldung bei einem SIP-Server automatisch Windows-Anmeldeinformationen zu verwenden.  <br/> |
|Deaktivieren der Server Versionsüberprüfung (DisableServerCheck)  <br/> |Wenn Sie diese Richtlinie auf "1" festlegen, wird verhindert, dass Skype for Business den Servernamen und die Version überprüft, bevor Sie sich anmelden. Standardmäßig führt Skype for Business diese Prüfungen aus, bevor Sie sich anmelden.  <br/> |
|Aktivieren der Verwendung von Bits zum Herunterladen von Adressbuchdienst Dateien (EnableBitsForGalDownload)  <br/> |Ermöglicht Skype for Business die Verwendung von Bits (Background Intelligent Transfer Service) zum Herunterladen der Adressbuchdienste-Dateien.  <br/> |
|Konfigurieren des SIP-Sicherheitsmodus (EnableSIPHighSecurityMode)  <br/> |Ermöglicht Skype for Business das sichere Senden und empfangen von Chatnachrichten. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.  <br/> Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, können Skype for Business einen beliebigen Transport verwenden. Wenn jedoch TLS nicht verwendet wird und der Server Benutzer authentifiziert, müssen Skype for Business entweder NTLM oder Kerberos-Authentifizierung verwenden.  <br/> |
|Anfängliche Verzögerung des globalen Adressbuch Downloads (GalDownloadInitialDelay)  <br/> |Gibt den Zeitraum an, vor dem ein Download der globalen Adressliste (GAL) erfolgt. Der Standardwert ist 60 Minuten, was bedeutet, dass der Server den Download der GAL-Datei für einen zufälligen Zeitraum zwischen 0 und 60 Minuten verzögert.  <br/> |
|Verhindern der Ausführung von Skype for Business durch Benutzer (PreventRun)  <br/> |Hindert Benutzer daran, Skype for Business auszuführen. Diese Richtlinieneinstellung kann sowohl in der Computerkonfiguration als auch in der Benutzerkonfiguration vorgenommen werden, die Einstellung in der Computerkonfiguration hat jedoch Vorrang.  <br/> |
|Zulassen der Speicherung von Benutzerkennwörtern (SavePassword)  <br/> |Ermöglicht Skype for Business das Speichern von Kennwörtern.  <br/> |
|Konfigurieren des SIP-Komprimierungsmodus (SipCompression)  <br/> |Legt fest, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.  <br/> |
|Liste der vertrauenswürdigen Domänen (TrustModelData)  <br/> |Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.  <br/> |
   
Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.
  
**Rangfolge von Gruppenrichtlinien**

|**Vorrang**|**Ort oder Einstellungsmethode**|
|:-----|:-----|
|1   <br/> |Skype for Business Server-in-Band-prozielung  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE \software\policies\microsoft\office\16.0\lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER \software\policies\microsoft\office\16.0\lync  <br/> |
|4   <br/> |Das Dialogfeldoptionen in Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der Skype for Business administrativen Vorlagendateien

1. Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthält. Erstellen Sie den Stammordner für den zentralen Speicher beispielsweise auf dem Domänencontroller an folgendem Speicherort:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Bei diesem Verfahren wird davon ausgegangen, dass Sie mehrere Computer in Ihrer Domäne verwalten möchten. In diesem Fall speichern Sie die Vorlagen in einem zentralen Speicher im Ordner "SYSVOL" auf dem primären Domänencontroller. Dadurch wird ein replizierter zentraler Speicherort für administrative Domänen Vorlagen bereitgestellt. 
  
2. Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden möchten. Diese Unterordner enthalten die sprachspezifischen ADML-Ressourcendateien. Erstellen Sie an dieser Stelle beispielsweise einen Unterordner für Englisch (en-US) für Deutschland:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

