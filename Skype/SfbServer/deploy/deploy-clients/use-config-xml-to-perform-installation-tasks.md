---
title: Verwenden der Datei „config.xml“ zur Durchführung von Installationsaufgaben in Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Informationen zu die Datei Config.xml verwenden, um zusätzlich Hinweise zur Installation anzugeben.'
ms.openlocfilehash: f55683d672df890be8baf0ac7ca50b3170faf3d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-server-2015"></a>Verwenden der Datei „config.xml“ zur Durchführung von Installationsaufgaben in Skype for Business Server 2015
 
**Zusammenfassung:** Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.
  
Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:
  
- Angeben des Netzwerkinstallationspfads
    
- Auswählen der zu installierenden Produkte
    
- Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates
    
- Angeben von Installationsoptionen, z. B. Benutzername
    
- Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office
    
- Hinzufügen oder Entfernen von Sprachen in der Installation
    
Es wird empfohlen, dass Sie die Datei "config.xml" zum Konfigurieren von Skype für die automatische Installation von Business verwenden. 
  
Standardmäßig werden in der Datei Config.xml, die in der kernproduktordner gespeichert wird (beispielsweise \ _Produkt_. WW) weist das Installationsprogramm, um dieses Produkt zu installieren. Beispielsweise wird die Datei "config.xml" in den folgenden Ordner Skype für Unternehmen installiert:
  
- \\server\share\Skype15\Skype.ww \Config.xml
    
Die am häufigsten verwendeten für Skype für die Installation von Business Config.xml-Elemente sind in der folgenden Tabelle aufgeführt.
  
**Config.XML-Elemente**

|**Element**|**Beschreibung**|
|:-----|:-----|
|Konfiguration  <br/> |Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync (auch für Skype for Business-Clients geeignet)  <br/> |
|"OptionState"  <br/> | Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden. Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, dass die gemeinsam genutzte Komponenten enthält, die mit Outlook 2016 stören: <br/>  ID = "LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
|Anzeige  <br/> | Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende: <br/>  CompletionNotice = "Yes" | "No"(Standard) " <br/>  AcceptEula = "Yes" | "No"(Standard) " <br/> |
|Protokollierung  <br/> | Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende: <br/>  Type = "Off" | "Standard"(Standard) | "Verbose" <br/>  Template = " _Dateiname_.txt" (der Name der Protokolldatei)  <br/> |
|Einstellung  <br/> | Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:<br/>  Setting Id = " _Name_" (der Name der Windows Installer-Eigenschaft)  <br/>  Wert = " _Wert_" (der Wert der Eigenschaft zugewiesen)  <br/> |
|DistributionPoint  <br/> | Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:<br/>  Speicherort = " _Pfad_"  <br/> |
   
Das folgende Beispiel zeigt eine Datei Config.xml für eine typische automatische Installation von Skype für Unternehmen. 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Ausführliche Informationen zur Verwendung der Datei "config.xml" zum Ausführen von Office-Installation und Wartung Aufgaben finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).
  
## <a name="to-customize-the-configxml-file"></a>So passen Sie die Datei "Config.xml" an

1. Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.
    
2. Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.
    
3. Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation. Stellen Sie sicher, dass Sie die Kommentartrennzeichen entfernen "\<!--" und "–\>". Verwenden Sie z. B. die folgende Syntax:
    
  ```
  < DistributionPoint Location="\\server\share\Skype15" />
  ```

4. Speichern Sie die Datei Config.xml.
    

