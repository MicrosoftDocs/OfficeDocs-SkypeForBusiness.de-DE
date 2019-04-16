---
title: Quality of Service in Microsoft Teams-Clients
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Quality of Service (QoS) für Microsoft-Teams, Clients zu implementieren.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 101deb10cf3d86dbc97116cad269556683d03be4
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869846"
---
# <a name="set-qos-on-windows-clients"></a>Festlegen von QoS auf Windows-Clients

Sie können Richtlinienbasierte QoS innerhalb der Gruppenrichtlinien verwenden, um den Quellportbereich für den vordefinierten DSCP-Wert in der Teams Client festzulegen. Die Portbereiche in der folgenden Tabelle angegeben sind, als Ausgangspunkt zum Erstellen einer Richtlinie für jeden Workload.

_Anfängliche Portbereiche empfohlen_

Media-Datenverkehrstyp| Client-Quellportbereich |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000 – 50,019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50,020 – 50,039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50,040 – 50,059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | |

Konfigurieren Sie nach Möglichkeit, Richtlinienbasierte QoS-Einstellungen in ein Gruppenrichtlinienobjekt. Die folgenden Schritte sind sehr ähnlich [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für die Skype für Business Server-Clients](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), die über einige zusätzliche Details verfügt, die möglicherweise nicht erforderlich.

Zum Erstellen einer audio QoS-Richtlinie für die Domäne eingebundener Windows 10 Computer zuerst melden Sie sich an einem Computer, auf dem die Gruppenrichtlinien-Verwaltungskonsole installiert wurde. Öffnen Sie die Gruppenrichtlinien-Verwaltungskonsole (klicken Sie auf Start, zeigen Sie auf Verwaltung, und klicken Sie dann auf die Gruppenrichtlinien-Verwaltungskonsole), und führen Sie dann die folgenden Schritte aus:

1. Suchen Sie in der Gruppenrichtlinien-Verwaltungskonsole den Container, in dem die neue Richtlinie erstellt werden soll. Beispielsweise sollte alle Client-Computer in einer Organisationseinheit mit dem Namen **Clients**befinden, die neue Richtlinie in der Organisationseinheit Client erstellt werden.

2. Maustaste auf den entsprechenden Container, und klicken Sie dann auf **Erstellen Sie ein Gruppenrichtlinienobjekt in dieser Domäne, und Verknüpfen des Arbeitsbereichs hier**.

3. Klicken Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** Geben Sie im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK**.

4. Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **Bearbeiten**.

5. In den Gruppenrichtlinienverwaltungs-Editor, erweitern Sie **Computerkonfiguration**, erweitern Sie **Windows-Einstellungen**, mit der rechten Maustaste **Richtlinienbasierte QoS**, und klicken Sie dann auf **neue Richtlinie erstellen**.

6. Geben Sie im Dialogfeld **Richtlinienbasierte QoS** auf der ersten Seite einen Namen für die neue Richtlinie in das Feld **Name** ein. Wählen Sie die **DSCP-Wert angeben** , und legen Sie den Wert auf **46 fest**. Lassen Sie **Ausgehende Drosselungsrate angeben** deaktiviert, und klicken Sie dann auf **Weiter**.

7. Wählen Sie auf der nächsten Seite **nur Anwendungen mit diesem Namen ausführbare** und geben Sie den Namen **Teams.exe**, und klicken Sie dann auf **Weiter**. Diese Einstellung weist die Richtlinie nur übereinstimmenden Datenverkehr vom Client Teams priorisieren.

8. Stellen Sie auf der dritten Seite sicher, dass **alle Quell-IP-Adresse** und **einer beliebigen Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter**. Diese zwei Einstellungen stellen Sie sicher, dass Pakete verwaltet werden unabhängig vom Computer (IP-Adresse), die die Pakete gesendet, und welchen Computern (IP-Adresse) wird die Pakete empfangen.

9. Wählen Sie auf Seite vier **TCP und UDP** aus der Dropdownliste **Wählen Sie das Protokoll, dem diese QoS-Richtlinie angewendet wird** . TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) werden die am häufigsten verwendeten zwei Netzwerkprotokollen.

10. Wählen Sie unter der Überschrift **Geben Sie die Quellportnummer** **aus dieser Quellport oder der Bereich**. Geben Sie in das Textfeld zugehörige den Portbereich für audio Übertragungen reserviert. Angenommen, wenn Sie Ports 50000 über Ports 50019 für audio-Datenverkehr reserviert ist, geben Sie den Portbereich, der mit diesem Format: **50000:50019**. Klicken Sie auf **Fertig stellen**.

11. Wiederholen Sie die Schritte 5 bis 10, um Richtlinien für Video und Anwendung/Desktop freigeben, ersetzen die entsprechenden Werte in Schritt 6 und 10 zu erstellen.

Die neuen Richtlinien, die von die Ihnen erstellten werden nicht erst wirksam, Gruppenrichtlinien auf den Clientcomputern aktualisiert wurde. Obwohl Gruppenrichtlinien allein in regelmäßigen Abständen aktualisiert wurde, können Sie eine sofortige Aktualisierung erzwingen, durch die folgenden Schritte ausführen:

1. Öffnen Sie auf jedem Computer, für die Sie die Gruppenrichtlinie aktualisieren möchten eine Befehlskonsole. Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.

2. Geben Sie an der Befehlszeile

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Überprüfen Sie die DSCP-Auswahlmöglichkeiten in das Gruppenrichtlinienobjekt

Führen Sie die folgenden Schritte aus, um zu überprüfen, dass die Werte aus dem Gruppenrichtlinienobjekt festgelegt wurden.

1. Öffnen Sie eine Befehlskonsole. Stellen Sie sicher, dass die Befehlskonsole festgelegt ist, als Administrator ausführen.

2. Geben Sie an der Befehlszeile Folgendes ein:

   ``` powershell
   gpresult /R > gp.txt
   ```

   Dies einen Bericht generiert und in eine Textdatei mit dem Namen gp.txt zu senden. Alternativ können Sie den folgenden Befehl aus, um die gleichen Daten in einem besser lesbar HTML-Bericht mit dem Namen gp.html zu erzeugen eingeben:

   ``` powershell
   gpresult /H >gp.html
   ```

   ![Screenshot des Konsolenfenster des Befehls Gpresult.] (media/Qos-in-Teams-Image3.png "Screenshot des Konsolenfenster des Befehls Gpresult.")

3. Suchen Sie in der generierten Datei nach der Überschrift **Gruppenrichtlinienobjekte angewendet** , und stellen Sie sicher, dass die Namen der zuvor erstellten Gruppenrichtlinienobjekte in der Liste der Richtlinien angewendet werden.

4. Öffnen Sie den Registrierungs-Editor, und wechseln Sie zu:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Überprüfen Sie die Werte für die in Tabelle 4 aufgeführten Registrierungseinträge.

   _In Tabelle 4. Werte für Windows-Registrierungseinträge für QoS_

   |          Name          |  Typ  |    Daten     |
   |         :---:          |:---:   |    :---:    |
   |    Application Name    | REG_SZ |  Teams.exe  |
   |       DSCP Value       | REG_SZ |     46      |
   |        Local IP        | REG_SZ |     \*      |
   | Local IP Prefix Length | REG_SZ |     \*      |
   |       Local Port       | REG_SZ | 50000-50019 |
   |        Protokoll        | REG_SZ |     \*      |
   |       Remote IP        | REG_SZ |     \*      |
   |    Remote-IP-Präfix    | REG_SZ |     \*      |
   |      Remote Port       | REG_SZ |     \*      |
   |     Throttle Rate      | REG_SZ |     -1      |

5. Stellen Sie sicher, dass der Wert für den Anwendungsnamen-Eintrag für den Client korrekt ist, den Sie verwenden, und stellen Sie sicher, dass sowohl die DSCP-Wert und der lokalen Port Einträge die Einstellungen in das Gruppenrichtlinienobjekt aktualisiert.
