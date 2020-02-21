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
ms.openlocfilehash: 9a157d5492378771cf40a6438bbf8672efd01412
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Registrieren von Benutzern für die Smartcard-Authentifizierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-03_

Im Allgemeinen gibt es zwei Methoden für die Registrierung von Benutzern für die Smartcard-Authentifizierung. Die einfachere Methode besteht darin, dass Benutzer sich direkt für die Smartcard-Authentifizierung mithilfe der Webregistrierung registrieren, während die komplexere Methode einen Registrierungs-Agent verwendet. Dieses Thema konzentriert sich auf die Selbstregistrierung für Smartcard-Zertifikate.

Weitere Informationen zur Registrierung im Namen von Benutzern als Registrierungs-Agent finden Sie unter Registrieren für Zertifikate im Namen anderer Benutzer unter [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>So registrieren Sie Benutzer für die Smartcard-Authentifizierung

1.  Melden Sie sich mit den Anmeldeinformationen eines lync-aktivierten Benutzers bei der Windows 8-Workstation an.

2.  Starten Sie Internet Explorer.

3.  Wechseln Sie zur **Webregistrierungs Seite der Zertifizierungsstelle** (beispielsweise https://MyCA.contoso.com/certsrv)
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.

    
    </div>

4.  Wählen Sie auf der **Willkommens** Seite **ein Zertifikat anfordern**aus.

5.  Wählen Sie dann **Erweiterte Anforderung**aus.

6.  Wählen Sie **erstellen, und senden Sie eine Anforderung an diese Zertifizierungsstelle**.

7.  Wählen Sie **Smartcard-Benutzer** im Abschnitt **Zertifikatvorlage** aus, und schließen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten ab:
    
      - **Schlüsseloptionen** bestätigen die folgenden Einstellungen:
        
          - Optionsfeld " **neuen Tastenkombination erstellen** " auswählen
        
          - Wählen Sie für **CSP**die Option **Microsoft Base Smart Card Crypto Provider** aus.
        
          - Wählen Sie für die **Schlüsselverwendung** **Exchange** aus (Dies ist die einzige verfügbare Option).
        
          - Geben Sie für die **Schlüsselgröße** **2048**
        
          - Bestätigen, dass der **Name des automatischen Schlüsselcontainers** ausgewählt ist
        
          - Lassen Sie die anderen Felder deaktiviert.
    
      - Bestätigen Sie unter **zusätzliche Optionen** die folgenden Werte:
        
          - Für das **Anforderungs Format** wählen Sie **CMC**aus.
        
          - Für **Hash Algorithmus** wählen Sie **SHA1**aus.
        
          - Geben Sie für **Anzeige Name** das **Smardcard-Zertifikat**ein.

8.  Wenn Sie einen physischen Smartcard-Leser verwenden, legen Sie die Smartcard in das Gerät ein.

9.  Klicken Sie auf über **Mitteln** , um die Zertifikatanforderung zu senden.

10. Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen Smartcard verwendet wurde.
    
    <div>
    

    > [!NOTE]  
    > Der standardmäßige virtuelle Smartcard-PIN-Wert lautet "12345678".

    
    </div>

11. Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **dieses Zertifikat installieren** , um den Registrierungsvorgang abzuschließen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihre Zertifikatanforderung mit dem Fehler "dieser Webbrowser unterstützt nicht die Generierung von Zertifikatanforderungen" fehlschlägt, gibt es drei Möglichkeiten, das Problem zu beheben: 
    > <OL>
    > <LI>
    > <P>Aktivieren der Kompatibilitätsansicht in Internet Explorer</P>
    > <LI>
    > <P>Aktivieren Sie die Option Intranet-Einstellungen aktivieren in Internet Explorer</P>
    > <LI>
    > <P>Aktivieren Sie im Menü Internet Explorer Optionen die Einstellung alle Zonen auf Standardebene Zurücksetzen auf der Registerkarte Sicherheit.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

