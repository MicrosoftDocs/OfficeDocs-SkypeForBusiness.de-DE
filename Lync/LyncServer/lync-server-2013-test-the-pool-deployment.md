---
title: 'Lync Server 2013: Testen der Poolbereitstellung'
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
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Testen der Poolbereitstellung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-09-25_

Im folgenden Verfahren wird beschrieben, wie die Bereitstellung des Front-End-Pools getestet wird.

<div>

## <a name="to-test-the-pool-deployment"></a>So testen Sie die Pool Bereitstellung

1.  Verwenden Sie Active Directory-Computer und-Benutzer, um das Active Directory-Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (auf der die lync Server 2013-Systemsteuerung installiert ist) zur **CSAdministrator** -Gruppe hinzuzufügen.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur CsAdministors-Gruppe hinzufügen, wird beim Öffnen der lync Server-Systemsteuerung eine Fehlermeldung angezeigt, die besagt, dass "nicht autorisiert: der Zugriff verweigert wird, weil ein Autorisierungsfehler bei der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC)" vorliegt.

    
    </div>

2.  Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    <div>
    

    > [!NOTE]  
    > Das Benutzerkonto kann nicht der lokale Administrator eines Servers sein, auf dem lync Server 2013 ausgeführt wird.

    
    </div>

3.  Verwenden Sie das Administratorkonto, um sich bei dem Computer anzumelden, auf dem die lync Server-Systemsteuerung installiert ist.

4.  Starten Sie die lync Server-Systemsteuerung, und geben Sie dann die Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden. In der lync Server-Systemsteuerung werden Bereitstellungsinformationen angezeigt.

5.  Klicken Sie in der linken Navigationsleiste auf **Topologie**, und stellen Sie dann sicher, dass der Dienststatus einen Computer mit einem grünen Pfeil anzeigt und ein grünes Häkchen für den Replikationsstatus neben jeder lync Server-Serverrolle vorhanden ist, die bereitgestellt und online geschaltet wurde.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** und dann auf **Benutzer aktivieren**.

7.  Klicken Sie auf der Seite **neuer lync Server-Benutzer** auf **Hinzufügen**.

8.  Wenn Sie Suchparameter für die zu ermittelnden Objekte definieren möchten, aktivieren Sie auf der Seite **Aus Active Directory auswählen** die Option **Suchen** und klicken Sie optional auf **Filter hinzufügen**. Alternativ können Sie auch die Option **LDAP-Suche** aktivieren und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken. Nachdem Sie sich für Ihre Suchoptionen entschieden haben, **Suchen**Sie nach dem Klirren.

9.  Wählen Sie im Bereich Suchergebnisse alle Objekte für diese Suchsitzung aus, und klicken Sie dann auf **OK**.

10. Auf der **neuen lync Server-Benutzer** Seite befinden sich die ausgewählten Objekte in der Ansicht **Benutzer** . Wählen Sie in der Liste **Benutzer einem Pool zuweisen** den Server aus, auf dem die Objekte verwaltet werden sollen.
    
    Im folgenden finden Sie eine Reihe von Optionen zum Konfigurieren der Objekte.
    
      - **SIP-URI für den Benutzer generieren**
    
      - **Telefonie**
    
      - **Anschluss-URI**
    
      - **Konferenzrichtlinie**
    
      - **Clientversionsrichtlinie**
    
      - **PIN-Richtlinie**
    
      - **Externe Zugriffsrichtlinie**
    
      - **Archivierungsrichtlinie**
    
      - **Standortrichtlinie**
    
      - **Clientrichtlinie**
    
    Wenn Sie die grundlegenden Funktionen testen möchten, wählen Sie die gewünschte Option für die **SIP-URI-Einstellung des Benutzers generieren** aus (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf **aktivieren**.

11. Eine Zusammenfassungsseite wird angezeigt, die ein Häkchen in der Spalte " **aktiviert** " zeigt, um anzugeben, dass die Objekte nun einsatzbereit sind. In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie zur Konfiguration der Benutzeranmeldung benötigen.

12. Melden Sie einen Benutzer auf einem Computer, der mit der Domäne verbunden ist, und einem anderen Benutzer auf einem anderen Computer in der Domäne an.

13. Installieren Sie lync 2013 auf jedem der beiden Clientcomputer, und überprüfen Sie, ob sich beide Benutzer bei lync Server 2013 anmelden können, und können Sie sich gegenseitig Sofortnachrichten senden.

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

