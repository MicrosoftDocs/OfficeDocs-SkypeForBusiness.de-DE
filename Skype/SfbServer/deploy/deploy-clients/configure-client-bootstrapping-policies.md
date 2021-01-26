---
title: Konfigurieren von Richtlinien für das Client-Bootstrapping
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Zusammenfassung: Verwalten von Gruppenrichtlinien.'
ms.openlocfilehash: 5d5a2d3a7939f34bb42995bb69280fb7891736ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805985"
---
# <a name="configure-client-bootstrapping-policies"></a>Konfigurieren von Richtlinien für das Client-Bootstrapping
 
**Zusammenfassung:** Verwalten von Gruppenrichtlinien.
  
Die Gruppenrichtlinienverwaltungskonsole (Group Policy Management Console, GPMC) und der Editor für Gruppenrichtlinienobjekte sind Tools, die Sie zum Verwalten von Gruppenrichtlinien verwenden. In der administrativen Vorlage für Office-Gruppenrichtlinien sind administrative Vorlagen für lync16.admx (ADMX) und ADML (ADML) enthalten, die die registrierungsbasierten Richtlinieneinstellungen für Skype for Business enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. Bei den ADML-Dateien handelt es sich um sprachspezifische Ergänzungen zu ADMX-Dateien. Jede ADMX- und -ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung. Sie können [die administrativen Vorlagendateien für Office 2016 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) kostenlos aus dem Microsoft Download Center herunterladen.
  
Für Skype for Business-Clients gibt es mehrere Richtlinien für das Clientboottrapping, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden. Beispielsweise die Standardserver und der Sicherheitsmodus, die der Client verwenden sollte, bis die Anmeldung abgeschlossen ist. Mithilfe von Gruppenrichtlinien können Sie diese Einstellungen in den Computerregistrierungen der Benutzer einrichten, bevor sie sich anmelden und mit dem Empfangen von In-Band-Bereitstellungseinstellungen vom Server beginnen. In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für Skype for Business verfügbar sind.
  
**Gruppenrichtlinieneinstellungen für Skype for Business**

|Gruppenrichtlinieneinstellung|Beschreibung|
|:-----|:-----|
|Angeben von Server (ConfigurationMode)  <br/> | Gibt an, wie Skype for Business den transport- und server identifiziert, der bei der Anmeldung verwendet werden soll. In dieser Einstellung geben Sie Folgendes an: <br/>  ServerAddressExternal: Gibt den Servernamen oder die IP-Adresse an, der von Clients und Partnerkontakten beim Herstellen einer Verbindung von außerhalb der externen Firewall verwendet wird. <br/>  ServerAddressInternal: Gibt den Servernamen oder die IP-Adresse an, der verwendet wird, wenn Clients eine Verbindung von innerhalb der Firewall der Organisation herstellen. <br/>  Transport: Gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an. <br/> |
|Zusätzliche unterstützte Serverversionen (ConfiguredServerCheckValues)  <br/> |Gibt eine Liste der Serverversionsnamen an, die durch Semikolon getrennt sind, an der skype for Business Server sich anmeldet, zusätzlich zu den Serverversionen, die standardmäßig unterstützt werden.  <br/> |
|Deaktivieren des automatischen Uploads von Anmeldefehlerprotokollen (DisableAutomaticSendTracing)  <br/> |Lädt Anmeldefehlerprotokolle automatisch zur Analyse in Skype for Business Server hoch. Bei erfolgreicher Anmeldung werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:  <br/> Für Skype for Business Online-Benutzer: Anmeldefehlerprotokolle werden automatisch hochgeladen. Für lokale Skype for Business-Benutzer: Dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt. Wenn diese Einstellung deaktiviert ist, werden Anmeldeprotokolle automatisch auf den Skype for Business Server für lokale Skype for Business- und Skype for Business Online-Benutzer hochgeladen. Wenn diese Einstellung aktiviert ist, werden Anmeldeprotokolle nie automatisch hochgeladen.  <br/> |
|Deaktivieren des HTTP-Fallbacks für die SIP-Verbindung (DisableHttpConnect)  <br/> |Verhindert, dass Skype for Business Server versucht, mithilfe von HTTP eine Verbindung mit dem Server herzustellen, wenn TLS oder TCP nicht verfügbar sind. Standardmäßig versucht Skype for Business zunächst, mithilfe von TLS oder TCP eine Verbindung mit dem Server herzustellen. Wenn keine dieser Transportmethoden erfolgreich ist, versucht Skype for Business, eine Verbindung über HTTP herzustellen. Verwenden Sie diese Richtlinie, um die Fallbackoption für den HTTP-Verbindungsversuch zu deaktivieren.  <br/> |
|Anmeldeinformationen erforderlich (DisableNTCredentials)  <br/> |Erfordert, dass der Benutzer Anmeldeinformationen für Skype for Business anstatt automatisch bei der Anmeldung bei einem SIP-Server verwendet.  <br/> |
|Deaktivieren der Serverversionsprüfung (DisableServerCheck)  <br/> |Wenn Sie diese Richtlinie auf 1 festlegen, wird verhindert, dass Skype for Business den Servernamen und die Version vor der Anmeldung überprüft. Standardmäßig nimmt Skype for Business diese Überprüfungen vor der Anmeldung vor.  <br/> |
|Aktivieren der Verwendung von BITS zum Herunterladen von Adressbuchdienstdateien (EnableBitsForGalDownload)  <br/> |Ermöglicht Skype for Business die Verwendung Background Intelligent Transfer Service (BITS) zum Herunterladen der Adressbuchdienstdateien.  <br/> |
|Konfigurieren des SIP-Sicherheitsmodus (EnableSIPHighSecurityMode)  <br/> |Ermöglicht Skype for Business das sichere Senden und Empfangen von Chatnachrichten. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.  <br/> Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, kann Skype for Business einen beliebigen Transport verwenden. Wenn TLS jedoch nicht verwendet wird und der Server Benutzer authentifiziert, muss Skype for Business entweder die NTLM- oder die Kerberos-Authentifizierung verwenden.  <br/> |
|Anfängliche Verzögerung beim Herunterladen des globalen Adressbuchs (GalDownloadInitialDelay)  <br/> |Gibt den Zeitraum vor dem Herunterladen der globalen Adressliste (GAL) an. Der Standardwert beträgt 60 Minuten, was bedeutet, dass der Server den Download der GAL-Datei für einen zufälligen Zeitraum zwischen 0 und 60 Minuten verzögert.  <br/> |
|Verhindern, dass Benutzer Skype for Business ausführen (PreventRun)  <br/> |Verhindert, dass Benutzer Skype for Business ausführen. Diese Richtlinieneinstellung kann sowohl in der Computerkonfiguration als auch in der Benutzerkonfiguration vorgenommen werden, die Einstellung in der Computerkonfiguration hat jedoch Vorrang.  <br/> |
|Zulassen der Speicherung von Benutzerkennwörtern (SavePassword)  <br/> |Ermöglicht Skype for Business das Speichern von Kennwörtern.  <br/> |
|Konfigurieren des SIP-Komprimierungsmodus (SipCompression)  <br/> |Legt fest, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.  <br/> |
|Liste vertrauenswürdiger Domänen (TrustModelData)  <br/> |Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der Kunden-SIP-Domäne übereinstimmen.  <br/> |
   
Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.
  
**Rangfolge von Gruppenrichtlinien**

|**Rangfolge**|**Ort oder Einstellungsmethode**|
|:-----|:-----|
|1   <br/> |Skype for Business Server-In-Band-Bereitstellung  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |Das Dialogfeld "Optionen" in Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der administrativen Vorlagendateien für Skype for Business

1. Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthält. Erstellen Sie den Stammordner für den zentralen Speicher beispielsweise auf dem Domänencontroller an folgendem Speicherort:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Bei diesem Verfahren wird davon ausgegangen, dass Sie mehrere Computer in Ihrer Domäne verwalten möchten. In diesem Fall speichern Sie die Vorlagen in einem zentralen Speicher im Ordner "Sysvol" auf dem primären Domänencontroller. Dies stellt einen replizierten zentralen Speicherort für administrative Domänenvorlagen bereit. 
  
2. Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden werden. Diese Unterordner enthalten die sprachspezifischen ADML-Ressourcendateien. Erstellen Sie z. B. an diesem Speicherort einen Unterordner für Englisch (USA) (EN-US):
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

