---
title: Konfigurieren von Richtlinien für das Client-Bootstrapping
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Zusammenfassung: Verwalten von Gruppenrichtlinien'
ms.openlocfilehash: 29e60ea772348ed5f483669cc1d17f8c13e96a02
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286537"
---
# <a name="configure-client-bootstrapping-policies"></a>Konfigurieren von Richtlinien für das Client-Bootstrapping
 
**Zusammenfassung:** Verwalten von Gruppenrichtlinien
  
Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools zur Verwaltung von Gruppenrichtlinien. In der administrativen Vorlage für Office-Gruppenrichtlinien sind lync16. ADMX-und ADML (ADML)-administrative Vorlagen enthalten, die die registrierungsbasierten Richtlinieneinstellungen für Skype for Business enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. ADML-Dateien sind sprachspezifische Komplemente für ADMX-Dateien. Jede ADMX- und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung. Sie können [die Office 2016 administrative Template-Dateien (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) kostenlos vom Microsoft Download Center herunterladen.
  
Für Skype for Business-Clients gibt es mehrere Richtlinien für Client-Bootstrapping, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden. Dazu gehören die Standardserver und der Sicherheitsmodus, die der Client bis zum Abschluss der Anmeldung verwenden soll. Sie können Gruppenrichtlinien verwenden, um diese Einstellungen in den Computer Registern der Benutzer festzulegen, bevor Sie sich anmelden und die Einstellungen für die in-Band-Bereitstellung vom Server empfangen. In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für Skype for Business zur Verfügung stehen.
  
**Gruppenrichtlinieneinstellungen für Skype for Business**

|Gruppenrichtlinieneinstellung|Beschreibung|
|:-----|:-----|
|Server angeben (ConfigurationMode)  <br/> | Gibt an, wie Skype for Business den Transport und den Server identifiziert, die bei der Anmeldung zu verwenden sind. In dieser Einstellung geben Sie Folgendes an: <br/>  ServerAddressExternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die von Clients und Verbundkontakten verwendet wird, um von außerhalb der Firewall eine Verbindung herzustellen. <br/>  ServerAddressInternal: gibt den Servernamen oder die IP-Adresse an, die verwendet wird, wenn Clients innerhalb der Firewall der Organisation eine Verbindung herstellen. <br/>  Transport: Gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an. <br/> |
|Unterstützte zusätzliche Server Versionen (ConfiguredServerCheckValues)  <br/> |Gibt eine Liste der Server Versionsnamen an, die durch Semikolons getrennt sind, bei denen sich Skype for Business Server zusätzlich zu den standardmäßig unterstützten Server Versionen anmeldet.  <br/> |
|Automatisches Hochladen von Anmeldefehlerprotokollen deaktivieren (DisableAutomaticSendTracing)  <br/> |Automatisches Hochladen von Anmeldefehler Protokollen in Skype for Business Server zur Analyse. Bei erfolgreichen Anmeldungen werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:  <br/> Für Skype for Business Online-Benutzer: Anmeldefehler Protokolle werden automatisch hochgeladen. Für Skype for Business-lokale Benutzer: dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt. Wenn diese Einstellung deaktiviert ist, werden Anmelde Protokolle automatisch auf den Skype for Business-Server hochgeladen, sowohl für Skype for Business lokal als auch für Skype for Business Online-Benutzer. Wenn diese Einstellung aktiviert ist, werden Anmeldeprotokolle niemals automatisch hochgeladen.  <br/> |
|Deaktivieren des http-Fallbacks für SIP-Verbindung (DisableHttpConnect)  <br/> |Verhindert, dass Skype for Business Server versucht, eine Verbindung mit dem Server über HTTP herzustellen, wenn TLS oder TCP nicht verfügbar sind. Standardmäßig versucht Skype for Business zunächst, mithilfe von TLS oder TCP eine Verbindung mit dem Server herzustellen, und wenn keine dieser Transportmethoden erfolgreich ist, versucht Skype for Business, eine Verbindung über HTTP herzustellen. Verwenden Sie diese Richtlinie, um den Fall Back http-Verbindungsversuch zu deaktivieren.  <br/> |
|Anfordern von Anmeldeinformationen (DisableNTCredentials)  <br/> |Erfordert, dass der Benutzeranmeldeinformationen für Skype for Business bereitstellt, anstatt die Windows-Anmeldeinformationen bei der Anmeldung bei einem SIP-Server automatisch zu verwenden.  <br/> |
|Deaktivieren der Server Versionsüberprüfung (DisableServerCheck)  <br/> |Wenn Sie diese Richtlinie auf 1 festlegen, wird verhindert, dass Skype for Business den Servernamen und die Version überprüft, bevor Sie sich anmelden. Standardmäßig führt Skype for Business diese Prüfungen durch, bevor Sie sich anmelden.  <br/> |
|Aktivieren der Verwendung von Bits zum Herunterladen von Adressbuchdienst Dateien (EnableBitsForGalDownload)  <br/> |Ermöglicht Skype for Business die Verwendung von Bits (Background Intelligent Transfer Service) zum Herunterladen der Adressbuchdienste-Dateien.  <br/> |
|Konfigurieren des SIP-Sicherheitsmodus (EnableSIPHighSecurityMode)  <br/> |Ermöglicht Skype for Business das sichere Senden und empfangen von Sofortnachrichten. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.  <br/> Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, kann Skype for Business beliebige Transporte verwenden. Wenn Sie aber nicht TLS verwenden und der Server Benutzer authentifiziert, muss Skype for Business entweder NTLM-oder Kerberos-Authentifizierung verwenden.  <br/> |
|Download des globalen Adressbuchs Initial Delay (GalDownloadInitialDelay)  <br/> |Legt den Zeitraum bis zum Download der globalen Adressliste (GAL) fest. Der Standardwert beträgt 60 Minuten, d. h., der Server verzögert den Download der globalen Adressliste um einen zufälligen Zeitraum zwischen 0 und 60 Minuten.  <br/> |
|Verhindern, dass Benutzer Skype for Business ausführen (PreventRun)  <br/> |Verhindert, dass Benutzer Skype for Business ausführen. Sie können diese Richtlinieneinstellung unter Computerkonfiguration und Benutzerkonfiguration konfigurieren, aber die Richtlinieneinstellung unter Computerkonfiguration hat Vorrang.  <br/> |
|Speichern von Benutzerkennwörtern zulassen (SavePassword)  <br/> |Ermöglicht es Skype for Business, Kennwörter zu speichern.  <br/> |
|Konfigurieren des SIP-Komprimierungsmodus (SipCompression)  <br/> |Gibt an, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.  <br/> |
|Liste der vertrauenswürdigen Domänen (TrustModelData)  <br/> |Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.  <br/> |
   
Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.
  
**Rangfolge von Gruppenrichtlinien**

|**Rangfolge**|**Ort oder Einstellungsmethode**|
|:-----|:-----|
|1  <br/> |Skype for Business Server-in-Band-Bereitstellung  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Dialogfeld ' Optionen ' in Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der administrativen Vorlagendateien von Skype for Business

1. Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthalten soll. Erstellen Sie beispielsweise den Stammordner für den zentralen Speicher auf Ihrem Domänencontroller an folgendem Speicherort:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Bei diesem Verfahren wird angenommen, dass Sie in Ihrer Domäne mehrere Computer verwalten möchten. Speichern Sie in diesem Fall die Vorlagen in einem zentralen Speicher im Ordner "Sysvol" auf dem primären Domänencontroller. Dies schafft einen replizierten zentralen Speicherort für administrative Domänenvorlagen. 
  
2. Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden möchten. Diese Unterordner enthalten die sprachenspezifischen ADML-Ressourcendateien. Erstellen Sie beispielsweise einen Unterordner für Englisch – USA (EN-US) an folgendem Speicherort:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

