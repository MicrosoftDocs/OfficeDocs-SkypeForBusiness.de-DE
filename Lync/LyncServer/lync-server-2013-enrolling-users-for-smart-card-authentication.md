---
title: 'Lync Server 2013: Registrieren von Benutzern für die Smartcard-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Registrieren von Benutzern für die Smartcard-Authentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-03_

Allgemein bestehen zwei Verfahren für das Registrieren von Benutzern für die SmartCard-Authentifizierung. Das einfachere Verfahren sieht die direkte Registrierung der Benutzer für die SmartCard-Authentifizierung mithilfe der Webregistrierung vor, während bei der komplexeren Methode ein Enrollment Agent verwendet wird. Dieses Thema legt den Schwerpunkt auf die Selbstregistrierung der Benutzer für SmartCard-Zertifikate.

Weitere Informationen zur Registrierung für Benutzer als Registrierungs-Agent finden Sie unter Registrieren für Zertifikate im Auftrag anderer Benutzer unter [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>So registrieren Sie Benutzer für die SmartCard-Authentifizierung

1.  Melden Sie sich mit den Anmeldeinformationen eines lync-fähigen Benutzers bei der Windows 8-Workstation an.

2.  Starten Sie Internet Explorer.

3.  Navigieren Sie zur **Website Registrierungs** Seite für die Zertifizierungsstelle https://MyCA.contoso.com/certsrv)(z. b.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.

    
    </div>

4.  Wählen Sie auf der Seite **Willkommen** die Option **Zertifikat anfordern** aus.

5.  Wählen Sie im nächsten Schritt **Erweiterte Anforderung** aus.

6.  Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** aus.

7.  Wählen Sie im Abschnitt **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus und füllen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten aus:
    
      - **Schlüsseloptionen** – bestätigen Sie die folgenden Einstellungen:
        
          - Aktivieren Sie das Optionsfeld **Neuen Schlüsselsatz erstellen**
        
          - Wählen Sie für **CSP** die Option **Microsoft Basis-SmartCard-Krypto-Anbieter**
        
          - Wählen Sie für **Schlüsselverwendung** den Wert **Exchange** aus (dies ist die einzige verfügbare Option).
        
          - Geben Sie unter **Schlüsselgröße** den Wert **2048** ein
        
          - Überprüfen Sie, ob **Automatischer Schlüsselcontainername** aktiviert ist
        
          - Lassen Sie die anderen Felder deaktiviert.
    
      - Bestätigen Sie unter **Weitere Optionen** die folgenden Werte:
        
          - Wählen Sie für **Anforderungsformat** den Wert **CMC** aus.
        
          - Wählen Sie für **Hashalgorithmus** den Wert **sha1** aus.
        
          - Geben Sie als **Anzeigename** den Wert **Smardcard Certificate** ein.

8.  Wenn Sie ein physisches Smartcard-Lesegerät verwenden, setzen Sie die SmartCard in das Gerät ein.

9.  Klicken Sie auf **Senden**, um die Zertifikatanforderung einzureichen.

10. Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen SmartCard verwendet wurde.
    
    <div>
    

    > [!NOTE]  
    > Der Standardwert der PIN für virtuelle SmartCards ist „12345678“.

    
    </div>

11. Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.
    
    <div>
    

    > [!NOTE]  
    > Wenn bei der Zertifikatanforderung ein Fehler mit der Meldung „Der Webbrowser unterstützt nicht die Generierung von Zertifikatanforderungen“ auftritt, kann das Problem auf drei verschiedene Weisen gelöst werden: 
    > <OL>
    > <LI>
    > <P>Aktivieren Sie in Internet Explorer die Kompatibilitätsansicht</P>
    > <LI>
    > <P>Aktivieren Sie die Option „Intraneteinstellungen einschalten“ in Internet Explorer</P>
    > <LI>
    > <P>Aktivieren Sie in den Internet Explorer-Optionen auf der Registerkarte „Sicherheit“ die Einstellung „Alle Zonen auf Standardstufe zurücksetzen“.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

