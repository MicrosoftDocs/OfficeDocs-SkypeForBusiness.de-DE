---
title: Zusammenführen mithilfe des Zusammenführungs-Assistenten für Topologie-Generator
description: Zusammenführen mithilfe des Zusammenführungs-Assistenten für Topologie-Generator.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d71a63eef95e3e36802dedfa9fbc1a173d283b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544561"
---
# <a name="merge-using-topology-builder-merge-wizard"></a>Zusammenführen mithilfe des Zusammenführungs-Assistenten für Topologie-Generator

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

1.  Laden Sie die vorhandene Bereitstellung mithilfe des Topologie-Generators herunter.

2.  Klicken Sie im Menü **Aktion** auf **Office Communications Server 2007 R2 zusammenführen**.

3.  Klicken Sie auf **Weiter**.

4.  Klicken Sie auf der Seite **Edgesetup angeben** auf **Hinzufügen**.
    
    ![Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Zusammenführungs Topologie-Assistent, Seite "Edge-Setup angeben"")  

5.  Geben Sie in **Edgesetup angeben** den Typ der Edgeserverkonfiguration ein, und klicken Sie auf **Weiter**. In diesem Beispiel wird die Option **Einzelner Edgeserver** verwendet.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Erweiterte Edgebereitstellung</STRONG> ist keine unterstützte Konfiguration. Ein <STRONG>Erweiterter Edgeserver</STRONG> muss zuerst in einen <STRONG>Einzelnen Edgeserver</STRONG> oder ein <STRONG>Konsolidiertes Edge mit Lastenausgleich</STRONG> umgewandelt werden.

    
    </div>

6.  Geben Sie unter **interne Edge-Einstellungen angeben** die relevanten Informationen für den internen FQDN des Edgepool und die Ports bei Bedarf ein, und klicken Sie dann auf **weiter**.
    
    ![Dialogfeld "interne Edge-Einstellungen angeben"](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Dialogfeld "interne Edge-Einstellungen angeben"")  

7.  Geben Sie in **Externen Edge angeben** die FQDN-Informationen für Webkonferenzen für Ihren Edgeserver ein.
    
    <div>
    

    > [!IMPORTANT]  
    > Führen Sie den nächsten Schritt dieses Verfahrens aus, bevor Sie auf <STRONG>Weiter</STRONG> klicken. Dieser Schritt darf auf keinen Fall ausgelassen werden.

    
    </div>

8.  Aktivieren Sie das Kontrollkästchen **diese Edgepool wird für Verbund-und öffentliche Instant Messaging-Konnektivität verwendet** , wenn Sie die Legacy Office Communications Server 2007 R2 Edgeserver für den Verbund verwenden möchten. Bei Bereitstellung mehrerer Edgeserver wird nur einer dieser Server für den Partnerverbund aktiviert. Wenn Sie dieses Kontrollkästchen nicht aktivieren und den Partnerverbund zu einem späteren Zeitpunkt aktivieren möchten, müssen Sie den Zusammenführungs-Assistenten des Topologie-Generators ausführen und Ihre Topologie erneut veröffentlichen.
    
    ![Edgeserver Dialogfeld, Seite "externer Edge" angeben](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edgeserver Dialogfeld, Seite "externer Edge" angeben")  

9.  Geben Sie auf der Seite **Nächsten Hop angeben** den vollqualifizierten Domänennamen (FQDN) des nächsten Hop-Standorts in Ihrer Umgebung ein. Klicken Sie auf **Fertig stellen**.
    
    ![Edgeserver Dialogfeld: Seite "Nächster Hop angeben"](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edgeserver Dialogfeld: Seite "Nächster Hop angeben"")  

10. Wenn Sie in " **Edge-Setup angeben**" alle Office Communications Server 2007 R2-Edgeserver hinzugefügt haben, klicken Sie auf **weiter**. Wenn Sie weitere Office Communications Server 2007 R2-Edgeserver hinzufügen möchten, wiederholen Sie dieses Verfahren ab Schritt 4.

11. Wählen Sie unter **interner SIP-Port angeben** die Standardeinstellung aus (also, wenn Sie den standardmäßigen SIP-Port nicht geändert haben). Ändern Sie den Port entsprechend, wenn Sie nicht den Standardport 5061 verwenden, und klicken Sie dann auf **Weiter**.

12. Klicken Sie auf der Seite **Zusammenfassung** auf **Weiter**, um mit dem Zusammenführen der Topologien zu beginnen.

13. Der Assistent überprüft, ob die Topologien erfolgreich zusammengeführt wurden.

14. Stellen Sie in der Spalte **Status** sicher, dass der Wert **Erfolg** lautet, und klicken Sie dann auf **Fertig stellen**.

15. Im linken Bereich des Topologie-Generators sollte nun das **BackCompatSite**angezeigt werden, das angibt, dass Ihre Office Communications Server 2007 R2 Umgebung mit lync Server 2013 zusammengeführt wurde.
    
    ![Topologie-Generator mit einer zusammengeführten Topologie](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topologie-Generator mit einer zusammengeführten Topologie")  

16. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **Weiter**.

17. Klicken Sie nach Abschluss des **Assistenten für die Veröffentlichung** auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Es ist wichtig, dass Sie das nächste Thema <A href="import-policies-and-settings.md">Importieren von Richtlinien und Einstellungen</A>durchführen, um sicherzustellen, dass die Legacyrichtlinien Einstellungen in lync Server 2013 importiert werden.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

