---
title: Mit "config.xml" zum Ausführen von Installationsaufgaben in Skype für Business-clients
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.'
ms.openlocfilehash: ea869fe2b49d5c1a5b4e04c3bc75cfd52b66555e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003508"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Mit "config.xml" zum Ausführen von Installationsaufgaben in Skype für Business-clients
 
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
  
**Config.xml-Elemente**

|**Element**|**Beschreibung**|
|:-----|:-----|
|Konfiguration  <br/> |Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync (auch für Skype for Business-Clients geeignet)  <br/> |
|"OptionState"  <br/> | Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden. Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, dass die freigegebene Komponenten umfasst, die Outlook beeinflussen: <br/>  ID = "LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
|Anzeige  <br/> | Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende: <br/>  CompletionNotice = "Yes" | "No"(Standard) " <br/>  AcceptEula = "Yes" | "No"(Standard) " <br/> |
|Protokollierung  <br/> | Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende: <br/>  Type = "Off" | "Standard"(Standard) | "Verbose" <br/>  Template = " _Dateiname_.txt" (der Name der Protokolldatei)  <br/> |
|Einstellung  <br/> | Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:<br/>  Setting Id = " _Name_" (der Name der Windows Installer-Eigenschaft)  <br/>  Wert = " _Wert_" (der Wert der Eigenschaft zugewiesen)  <br/> |
|DistributionPoint  <br/> | Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:<br/>  Speicherort = " _Pfad_"  <br/> |
   
Das folgende Beispiel zeigt eine Datei Config.xml für eine typische automatische Installation von der Skype für Business-Client. 
  
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
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. Speichern Sie die Datei Config.xml.
    

