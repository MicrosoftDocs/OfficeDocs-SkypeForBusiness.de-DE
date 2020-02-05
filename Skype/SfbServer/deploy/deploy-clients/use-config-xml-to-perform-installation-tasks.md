---
title: Verwenden von "config. xml" zum Ausführen von Installationsaufgaben in Skype for Business-Clients
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Zusammenfassung: Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.'
ms.openlocfilehash: a935e3623e99324eb24caef4e7e232d2311c5cfb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768648"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Verwenden von "config. xml" zum Ausführen von Installationsaufgaben in Skype for Business-Clients

**Zusammenfassung:** Wie die Datei „Config.xml“ verwendet wird, um weitere Installationshinweise anzugeben.

Das Office-Anpassungstool (OAT) ist zwar das primäre Tool für die angepasste Installation, Administratoren können jedoch mit der Datei "Config.xml" zusätzliche, im OAT nicht verfügbare Installationsanweisungen angeben. Die folgenden Anpassungen können nur mithilfe der Datei Config.xml vorgenommen werden:

- Angeben des Netzwerkinstallationspfads

- Auswählen der zu installierenden Produkte

- Konfigurieren der Protokollierung und des Speicherorts der Setupanpassungsdatei und Softwareupdates

- Angeben von Installationsoptionen, z. B. Benutzername

- Kopieren der lokalen Installationsquelle (Local Installation Source, LIS) auf den Benutzercomputer ohne Installation von Office

- Hinzufügen oder Entfernen von Sprachen in der Installation

Wir empfehlen, die Datei config. XML zum Konfigurieren der unbeaufsichtigten Installation von Skype for Business zu verwenden. 

Standardmäßig ist die Datei config. XML, die im Kernproduktordner gespeichert ist (beispielsweise \ _Product_. WW) weist Setup an, dieses Produkt zu installieren. Beispielsweise installiert die Datei config. XML im folgenden Ordner Skype for Business:

- \\server\share\Skype15\Skype.WW \Config.xml

Die am häufigsten für die Skype for Business-Installation verwendeten config. XML-Elemente sind in der folgenden Tabelle aufgelistet.

**Config.xml-Elemente**


| **Element**              | **Beschreibung**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfiguration  <br/>     | Element der obersten Ebene (erforderlich). Enthält das Produktattribut, z. B.: Product=Lync (auch für Skype for Business-Clients geeignet)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Gibt an, wie bestimmte Produktfeatures während der Installation behandelt werden. Verwenden Sie die folgenden Attribute, um die Installation von Business Connectivity Services zu verhindern, die freigegebene Komponenten umfasst, die Outlook stören: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Anzeige  <br/>           | Die Ebene der Benutzeroberfläche, die dem Benutzer angezeigt wird. Zu den typischen Attributen zählen Folgende: <br/>  CompletionNotice = "Ja"                                                                                                                                                                                |
| Protokollierung  <br/>           | Optionen für den vom Setup ausgeführten Protokollierungstyp. Zu den typischen Attributen zählen Folgende: <br/>  Geben Sie = "aus" ein.                                                                                                                                                                                       |
| Einstellung  <br/>           | Gibt Werte für Windows Installer-Eigenschaften an. Zu den typischen Attributen zählen Folgende:<br/>  Setting ID = " *Name*" (der Name der Windows Installer-Eigenschaft)  <br/>  Value = " *Wert*" (der Wert, der der Eigenschaft zugewiesen werden soll)  <br/>                                                             |
| DistributionPoint  <br/> | Der vollqualifizierte Pfad des Netzwerkinstallationspfads, von dem die Installation ausgeführt werden soll. Enthält das Standortattribut:<br/>  Location = " *path*"  <br/>                                                                                                                                     |

Das folgende Beispiel zeigt eine config. XML-Datei für eine typische unbeaufsichtigte Installation des Skype for Business-Clients. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Detaillierte Informationen zur Verwendung der Datei config. XML zum Ausführen von Office-Installations-und-Wartungs [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)Aufgaben finden Sie unter.

## <a name="to-customize-the-configxml-file"></a>So passen Sie die Datei "Config.xml" an

1. Öffnen Sie die Datei "Config.xml" in einem Text-Editor wie Editor.

2. Suchen Sie die Zeilen, die die zu ändernden Elemente enthalten.

3. Ändern Sie den Elementeintrag mit den gewünschten Optionen für eine automatische Installation. Stellen Sie sicher, dass Sie die Kommentartrennzeichen "\<!--" und "--\>" entfernen. Verwenden Sie z. B. die folgende Syntax:

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Speichern Sie die Datei Config.xml.


