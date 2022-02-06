---
title: Konfigurieren von Richtlinien für das Client-Bootstrapping
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Zusammenfassung: Verwalten von Gruppenrichtlinien.'
---

# <a name="configure-client-bootstrapping-policies"></a>Konfigurieren von Richtlinien für das Client-Bootstrapping
 
**Zusammenfassung:** Verwalten von Gruppenrichtlinien.
  
Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools, die Sie zum Verwalten von Gruppenrichtlinien verwenden. In der Office Administrativen Vorlage für Gruppenrichtlinien sind lync16.admx (ADMX) und ADML -Administrative Vorlagen enthalten, die die registrierungsbasierten Richtlinieneinstellungen für Skype for Business enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. ADML-Dateien sind sprachspezifische Ergänzungen zu ADMX-Dateien. Jede ADMX- und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office Anwendung. Sie können [die administrativen Vorlagendateien Office 2016 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) kostenlos aus dem Microsoft Download Center herunterladen.
  
Für Skype for Business Clients gibt es mehrere Client-Bootstrapping-Richtlinien, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden. Beispielsweise die Standardserver und der Sicherheitsmodus, den der Client verwenden soll, bis die Anmeldung abgeschlossen ist. Mithilfe von Gruppenrichtlinien können Sie diese Einstellungen in den Computerregistern der Benutzer einrichten, bevor sie sich anmelden und mit dem Empfang von In-Band-Bereitstellungseinstellungen vom Server beginnen. In der folgenden Tabelle sind die Gruppenrichtlinieneinstellungen aufgeführt, die für Skype for Business verfügbar sind.
  
**Gruppenrichtlinien-Einstellungen für Skype for Business**

|Gruppenrichtlinieneinstellung|Beschreibung|
|:-----|:-----|
|Specify Server (ConfigurationMode)  <br/> | Gibt an, wie Skype for Business den Transport und server identifiziert, der während der Anmeldung verwendet werden soll. In dieser Einstellung geben Sie Folgendes an: <br/>  ServerAddressExternal: Gibt den Servernamen oder die IP-Adresse an, der von Clients und Verbundkontakten verwendet wird, wenn eine Verbindung von außerhalb der externen Firewall hergestellt wird. <br/>  ServerAddressInternal: Gibt den Servernamen oder die IP-Adresse an, der verwendet wird, wenn Clients eine Verbindung innerhalb der Firewall der Organisation herstellen. <br/>  Transport: Gibt entweder TCP (Transmission Control Protocol) oder Transport Layer Security (TLS) an. <br/> |
|Weitere unterstützte Serverversionen (ConfiguredServerCheckValues)  <br/> |Gibt eine Liste der Serverversionsnamen an, die durch Semikolons getrennt sind, bei denen sich Skype for Business Server zusätzlich zu den standardmäßig unterstützten Serverversionen anmelden.  <br/> |
|Automatisches Hochladen von Anmeldefehlerprotokollen deaktivieren (DisableAutomaticSendTracing)  <br/> |Lädt Anmeldefehlerprotokolle automatisch zur Analyse in Skype for Business Server hoch. Bei erfolgreicher Anmeldung werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:  <br/> Für Skype for Business Onlinebenutzer: Anmeldefehlerprotokolle werden automatisch hochgeladen. Für Skype for Business lokale Benutzer: Dem Benutzer wird vor dem Hochladen ein Bestätigungsdialogfeld angezeigt. Wenn diese Einstellung deaktiviert ist, werden Anmeldeprotokolle sowohl für Skype for Business lokale benutzer als auch für Skype for Business Onlinebenutzer automatisch in die Skype for Business Server hochgeladen. Wenn diese Einstellung aktiviert ist, werden Anmeldeprotokolle nie automatisch hochgeladen.  <br/> |
|Deaktivieren des HTTP-Fallbacks für die SIP-Verbindung (DisableHttpConnect)  <br/> |Verhindert, dass Skype for Business Server versuchen, über HTTP eine Verbindung mit dem Server herzustellen, wenn TLS oder TCP nicht verfügbar sind. Standardmäßig versucht Skype for Business zuerst, eine Verbindung mit dem Server mithilfe von TLS oder TCP herzustellen. Wenn keine dieser Transportmethoden erfolgreich ist, Skype for Business versucht, eine Verbindung mithilfe von HTTP herzustellen. Verwenden Sie diese Richtlinie, um die Fallbackoption für den HTTP-Verbindungsversuch zu deaktivieren.  <br/> |
|Anmeldeinformationen erforderlich (DisableNTCredentials)  <br/> |Der Benutzer muss Anmeldeinformationen für Skype for Business angeben, anstatt während der Anmeldung bei einem SIP-Server automatisch Windows Anmeldeinformationen zu verwenden.  <br/> |
|Deaktivieren der Serverversionsprüfung (DisableServerCheck)  <br/> |Wenn Sie diese Richtlinie auf 1 festlegen, wird verhindert, dass Skype for Business vor der Anmeldung den Servernamen und die Serverversion überprüfen. Standardmäßig führt Skype for Business diese Überprüfungen vor der Anmeldung durch.  <br/> |
|Aktivieren der Verwendung von BITS zum Herunterladen von Adressbuchdienstdateien (EnableBitsForGalDownload)  <br/> |Ermöglicht Skype for Business die Verwendung von Background Intelligent Transfer Service (BITS), um die Adressbuchdienste-Dateien herunterzuladen.  <br/> |
|Konfigurieren des SIP-Sicherheitsmodus (EnableSIPHighSecurityMode)  <br/> |Ermöglicht Skype for Business, Chatnachrichten sicherer zu senden und zu empfangen. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.  <br/> Wenn Sie diese Richtlinieneinstellung nicht konfigurieren, können Skype for Business einen beliebigen Transport verwenden. Wenn jedoch kein TLS verwendet wird und der Server Benutzer authentifiziert, müssen Skype for Business entweder die NTLM- oder die Kerberos-Authentifizierung verwenden.  <br/> |
|Anfängliche Verzögerung beim Herunterladen des globalen Adressbuchs (GalDownloadInitialDelay)  <br/> |Gibt den Zeitraum vor dem Herunterladen der globalen Adressliste (GAL) an. Der Standardwert ist 60 Minuten, was bedeutet, dass der Server den Download der GAL-Datei um einen zufälligen Zeitraum zwischen 0 und 60 Minuten verzögert.  <br/> |
|Benutzer am Ausführen von Skype for Business hindern (PreventRun)  <br/> |Verhindert, dass Benutzer Skype for Business ausführen. Diese Richtlinieneinstellung kann sowohl in der Computerkonfiguration als auch in der Benutzerkonfiguration vorgenommen werden, die Einstellung in der Computerkonfiguration hat jedoch Vorrang.  <br/> |
|Speicherung von Benutzerkennwörtern zulassen (SavePassword)  <br/> |Ermöglicht Skype for Business das Speichern von Kennwörtern.  <br/> |
|Konfigurieren des SIP-Komprimierungsmodus (SipCompression)  <br/> |Legt fest, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.  <br/> |
|Liste der vertrauenswürdigen Domänen (TrustModelData)  <br/> |Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.  <br/> |
   
Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.
  
**Rangfolge von Gruppenrichtlinien**

|**Vorrang**|**Ort oder Einstellungsmethode**|
|:-----|:-----|
|1  <br/> |Skype for Business Server In-Band-Bereitstellung  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Das Dialogfeld "Optionen" in Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>So definieren Sie Gruppenrichtlinieneinstellungen mithilfe der Skype for Business administrativen Vorlagendateien

1. Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthält. Erstellen Sie den Stammordner für den zentralen Speicher beispielsweise auf dem Domänencontroller an folgendem Speicherort:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Bei diesem Verfahren wird davon ausgegangen, dass Sie mehrere Computer in Ihrer Domäne verwalten möchten. In diesem Fall speichern Sie die Vorlagen in einem zentralen Speicher im Ordner "Sysvol" auf dem primären Domänencontroller. Dadurch wird ein replizierter zentraler Speicherort für administrative Domänenvorlagen bereitgestellt. 
  
2. Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden werden. Diese Unterordner enthalten die sprachspezifischen ADML-Ressourcendateien. Erstellen Sie beispielsweise an diesem Speicherort einen Unterordner für Englisch (EN-US) für die USA:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

