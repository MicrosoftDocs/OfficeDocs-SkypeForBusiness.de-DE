---
title: 'Lync Server 2013: Testen der Pool Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 552677dde2706265093879bc9b48ac803e1365fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Testen der Pool Bereitstellung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-09-25_

Im folgenden Verfahren wird beschrieben, wie Sie die Bereitstellung des Front-End-Pool testen.

<div>

## <a name="to-test-the-pool-deployment"></a>So testen Sie die Pool Bereitstellung

1.  Verwenden Sie Active Directory Computer und Benutzer, um das Active Directory Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (in der lync Server 2013 Systemsteuerung installiert ist) zur Gruppe **CSAdministrator** hinzuzufügen.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur Gruppe CsAdministors hinzufügen, wird beim Öffnen von lync Server-Systemsteuerung eine Fehlermeldung angezeigt, die besagt, dass "nicht autorisiert: der Zugriff aufgrund eines RBAC-Autorisierungs Fehlers (Role-Based Access Control) verweigert wird."

    
    </div>

2.  Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    <div>
    

    > [!NOTE]  
    > Das Benutzerkonto kann nicht der lokale Administrator eines beliebigen Servers mit lync Server 2013 sein.

    
    </div>

3.  Melden Sie sich mit dem Administratorkonto bei dem Computer an, auf dem lync Server-Systemsteuerung installiert ist.

4.  Starten Sie lync Server-Systemsteuerung, und geben Sie dann bei Aufforderung Anmeldeinformationen ein. Lync Server-Systemsteuerung zeigt Bereitstellungsinformationen an.

5.  Klicken Sie in der linken Navigationsleiste auf **Topologie**, und vergewissern Sie sich dann, dass der Dienststatus einen Computer mit einem grünen Pfeil anzeigt und dass neben jeder lync Server Server Rolle, die bereitgestellt und online geschaltet wurde, ein grünes Häkchen für den Replikationsstatus ist.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und klicken Sie dann auf **Benutzer aktivieren**.

7.  Klicken Sie auf der Seite **neuer lync Server Benutzer** auf **Hinzufügen**.

8.  Zum Definieren von Suchparametern für die Objekte, die Sie suchen möchten, können Sie auf der Seite **Active Directory auswählen** die Option **Suche**auswählen und dann optional auf **Filter hinzufügen**klicken. Sie können auch **LDAP-Suche** auswählen und einen LDAP-Ausdruck eingeben, um die zurückzugebenden Objekte zu filtern oder einzuschränken. Nachdem Sie sich für Ihre Suchoptionen entschieden haben, **finden**Sie Klirren.

9.  Wählen Sie im Bereich Suchergebnisse alle Objekte für diese Suchsitzung aus, und klicken Sie dann auf **OK**.

10. Auf der Seite **neuer lync Server Benutzer** befinden sich die ausgewählten Objekte in der **Benutzer** Anzeige. Wählen Sie in der Liste **Benutzer einem Pool zuweisen** den Server aus, auf dem die Objekte verwaltet werden sollen.
    
    Im folgenden finden Sie eine Reihe von Optionen zum Konfigurieren der Objekte.
    
      - **SIP-URI des Benutzers generieren**
    
      - **Telefonie**
    
      - **Anschluss-URI**
    
      - **Konferenzrichtlinie**
    
      - **Client Versionsrichtlinie**
    
      - **PIN-Richtlinie**
    
      - **Richtlinie für den externen Zugriff**
    
      - **Archivierungsrichtlinie**
    
      - **Standortrichtlinie**
    
      - **Client Richtlinie**
    
    Zum Testen der grundlegenden Funktionalität wählen Sie die gewünschte Option für die **SIP-URI-Einstellung des Benutzers generieren** (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf **aktivieren**.

11. Eine Zusammenfassungsseite wird angezeigt, die ein Häkchen in der Spalte **aktiviert** zeigt, um anzugeben, dass die Objekte nun zur Verwendung bereit sind. In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie für die Benutzeranmelde Konfiguration benötigen.

12. Melden Sie einen Benutzer bei einem Computer an, der der Domäne beigetreten ist, und ein anderer Benutzer auf einem anderen Computer in der Domäne.

13. Installieren Sie lync 2013 auf den beiden Clientcomputern, und stellen Sie dann sicher, dass sich beide Benutzer bei lync Server 2013 anmelden und Sofortnachrichten miteinander senden können.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Clients und Geräten in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

