---
title: Konfigurieren von Richtlinien für das Client-Bootstrapping
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Zusammenfassung: Informationen zum Verwalten von Gruppenrichtlinien.'
ms.openlocfilehash: 8c7254d42de76150eb4f3910f3e5e400206e7acf
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967789"
---
# <a name="configure-client-bootstrapping-policies"></a>Konfigurieren von Richtlinien für das Client-Bootstrapping
 
**Zusammenfassung:** Informationen zum Verwalten von Gruppenrichtlinien.
  
Die Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) und der Gruppenrichtlinienobjekt-Editor sind Tools zur Verwaltung von Gruppenrichtlinien. Mit dem Office Administrative Vorlagen für Gruppenrichtlinien enthalten sind, lync16.admx (ADMX) und ADML (ADML) Administrative Vorlagen, die die registrierungsbasierte Richtlinieneinstellungen für Skype für Unternehmen enthalten, die Sie für Gruppenrichtlinienobjekte in der Domäne konfigurieren. ADML-Dateien sind sprachspezifische Komplemente für ADMX-Dateien. Jede ADMX- und ADML-Datei enthält die Richtlinieneinstellungen für eine einzelne Office-Anwendung. Sie können aus dem Microsoft Download Center kostenlos [herunterladen Office 2016 Administrative Vorlagendateien (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) .
  
Skype für Geschäftskunden stehen mehrere Client bootstrapping Policies, die Sie berücksichtigen sollten, bevor Benutzer auf den Server zum ersten Mal anmelden konfigurieren. Dazu gehören die Standardserver und der Sicherheitsmodus, die der Client bis zum Abschluss der Anmeldung verwenden soll. Sie können auch Gruppenrichtlinien verwenden, diese Einstellungen bei den Benutzern Computer Register herstellen, bevor sie anmelden und Empfangen von in-Band-bereitstellungseinstellungen vom Server beginnen. Die folgende Tabelle enthält die gruppenrichtlinieneinstellungen, die für Skype für Unternehmen verfügbar sind.
  
**Group Policy Settings for Skype für Unternehmen**

|Gruppenrichtlinieneinstellung|Beschreibung|
|:-----|:-----|
|Server angeben(ConfigurationMode) angeben  <br/> | Gibt an, wie Skype für Unternehmen Transportprotokoll und Server, die während der Anmeldung verwendet identifiziert. In dieser Einstellung geben Sie Folgendes an: <br/>  ServerAddressExternal: Gibt den Servernamen oder die IP-Adresse an, der bzw. die von Clients und Verbundkontakten verwendet wird, um von außerhalb der Firewall eine Verbindung herzustellen. <br/>  ServerAddressInternal: Gibt an, den Servernamen oder die IP-Adresse verwendet, wenn Clients von innerhalb der Firewall des Unternehmens eine Verbindung herstellen. <br/>  Transport: Gibt entweder TCP (Transmission Control Protocol) oder TLS (Transport Layer Security) an. <br/> |
|Zusätzliche unterstützte Serverversionen(configuredservercheckvalues)  <br/> |Gibt eine Liste mit Versionsnamen getrennt durch Semikolons ein, denen Skype für Business Server auf zusätzlich zu den Serverversionen, die standardmäßig unterstützt werden.  <br/> |
|Automatisches Hochladen von Anmeldefehlerprotokollen deaktivieren (DisableAutomaticSendTracing)  <br/> |Automatisch hochgeladen anmeldefehlerprotokolle Skype für Business Server für die Analyse. Bei erfolgreichen Anmeldungen werden keine Protokolle automatisch hochgeladen. Wenn diese Richtlinie nicht konfiguriert ist, geschieht Folgendes:  <br/> Für Skype für Business Online-Benutzer: Anmeldung anmeldefehlerprotokolle werden automatisch hochgeladen. Für Skype für Unternehmen Benutzern lokale-: dem Benutzer vor dem Hochladen ein Bestätigungsdialogfeld angezeigt wird. Wenn diese Einstellung deaktiviert ist, werden Protokolle-Anmeldung automatisch die Skype für Business Server für Skype für Business lokal und Skype für Business Onlinebenutzer hochgeladen. Wenn diese Einstellung aktiviert ist, werden Anmeldeprotokolle niemals automatisch hochgeladen.  <br/> |
|Deaktivieren von HTTP-fallback für SIP-Verbindung deaktivieren(disablehttpconnect)  <br/> |Verhindert, dass Skype für Business Server versucht, auf dem Server eine Verbindung über HTTP, wenn TLS oder TCP nicht verfügbar sind. In der Standardeinstellung Skype für Unternehmen zuerst versucht, auf dem Server eine Verbindung über TLS oder TCP und, wenn keiner dieser Transportmethoden erfolgreich ist, versucht Skype für Unternehmen eine Verbindung über HTTP. Verwenden Sie diese Richtlinie, um die fallback HTTP Verbindungsversuch zu deaktivieren.  <br/> |
|Benötigen Sie Anmeldeinformationen (DisableNTCredentials)  <br/> |Bewirkt, dass den Benutzer Anmeldeinformationen für Skype für Business, anstatt automatisch Windows-Anmeldeinformationen während der Anmeldung an einem SIP-Server verwendet werden.  <br/> |
|Deaktivieren von Server-versionsprüfung (DisableServerCheck)  <br/> |Wenn Sie diese Richtlinie auf 1 gesetzt, verhindert, dass Skype für Unternehmen überprüfen den Servernamen und die Version vor der Anmeldung. Standardmäßig ist Skype für Unternehmen diese Prüfungen vor dem anmelden.  <br/> |
|Aktivieren der Verwendung von BITS zum Herunterladen von Adressbuchdienst-Dateien aktivieren(enablebitsforgaldownload)  <br/> |Skype für Unternehmen intelligente Hintergrundübertragungsdienst (Background Intelligent Transfer Service, BITS) verwenden, um die Dateien der Adressbuchdienste herunterladen können.  <br/> |
|Konfigurieren von SIP-Sicherheitsmodus (EnableSIPHighSecurityMode)  <br/> |Skype für Unternehmen zum Senden und Empfangen von Sofortnachrichten sicherer ermöglicht. Diese Richtlinie hat keine Auswirkung auf Windows .NET- oder Microsoft Exchange Server-Dienste.  <br/> Wenn Sie diese Einstellung nicht konfigurieren, kann Skype für Unternehmen ein beliebiges Übertragungsprotokoll verwenden. Wenn TLS wird nicht verwendet, und wenn der Server Benutzer authentifiziert, Skype für Unternehmen muss jedoch verwenden NTLM oder Kerberos-Authentifizierung.  <br/> |
|Globales Adressbuch downloaden Verzögerung (GalDownloadInitialDelay)  <br/> |Legt den Zeitraum bis zum Download der globalen Adressliste (GAL) fest. Der Standardwert beträgt 60 Minuten, d. h., der Server verzögert den Download der globalen Adressliste um einen zufälligen Zeitraum zwischen 0 und 60 Minuten.  <br/> |
|Verhindern Sie, dass Benutzer Skype für Unternehmen (PreventRun)  <br/> |Verhindert, dass Benutzer Skype für Unternehmen ausgeführt werden. Sie können diese Einstellung unter Computerkonfiguration und Benutzerkonfiguration, aber die Einstellung unter Computerkonfiguration Vorrang.  <br/> |
|Speicherung von Benutzerkennwörtern (SavePassword)  <br/> |Skype für Unternehmen zum Speichern von Kennwörtern ermöglicht.  <br/> |
|Konfigurieren von SIP-Komprimierungsmodus (SipCompression)  <br/> |Gibt an, wann die SIP-Komprimierung aktiviert wird. Die SIP-Komprimierung wird standardmäßig auf Grundlage der Adaptergeschwindigkeit aktiviert. Beachten Sie, dass die Festlegung dieser Richtlinie die Anmeldezeit verlängern kann.  <br/> |
|Liste der vertrauenswürdigen Domäne (TrustModelData)  <br/> |Listet die vertrauenswürdigen Domänen auf, die nicht mit dem Präfix der SIP-Domäne des Kunden übereinstimmen.  <br/> |
   
Auf dem Server konfigurierte Richtlinien haben Vorrang vor Gruppenrichtlinieneinstellungen und Clientoptionen, die vom Benutzer konfiguriert wurden. In der folgenden Tabelle wird zusammengefasst, welche Einstellungen Vorrang haben, falls ein Konflikt auftritt.
  
**Rangfolge von Gruppenrichtlinien**

|**Rangfolge**|**Ort oder Einstellungsmethode**|
|:-----|:-----|
|1  <br/> |Skype für Business Server in-Band-Bereitstellung  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Das Dialogfeld "Optionen" in Skype für Unternehmen  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>So definieren Sie gruppenrichtlinieneinstellungen mithilfe der Skype für administrative Vorlagendateien für Business

1. Erstellen Sie einen Ordner auf Stammebene, der alle sprachneutralen ADMX-Dateien enthalten soll. Erstellen Sie beispielsweise den Stammordner für den zentralen Speicher auf Ihrem Domänencontroller an folgendem Speicherort:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Bei diesem Verfahren wird angenommen, dass Sie in Ihrer Domäne mehrere Computer verwalten möchten. Speichern Sie in diesem Fall die Vorlagen in einem zentralen Speicher im Ordner "Sysvol" auf dem primären Domänencontroller. Dies schafft einen replizierten zentralen Speicherort für administrative Domänenvorlagen. 
  
2. Erstellen Sie einen Unterordner für jede Sprache, die Sie verwenden möchten. Diese Unterordner enthalten die sprachenspezifischen ADML-Ressourcendateien. Erstellen Sie beispielsweise einen Unterordner für Englisch – USA (EN-US) an folgendem Speicherort:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

