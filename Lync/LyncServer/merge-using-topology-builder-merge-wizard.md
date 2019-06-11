---
title: Zusammenführen mit dem Zusammenführungs-Assistenten für Topologie-Generator
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a65dab8cb99b35821f12c5871ae52f608ae344
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Zusammenführen mit dem Zusammenführungs-Assistenten für Topologie-Generator

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

1.  Laden Sie die vorhandene Bereitstellung mithilfe von Topology Builder herunter.

2.  Wählen Sie im Menü **Aktion** die Option **Office Communications Server 2007 R2 zusammenführen**aus.

3.  Klicken Sie auf **Weiter**.

4.  Klicken Sie unter **Edge-Setup angeben**auf **Hinzufügen**.
    
    ![Assistenten für die Zusammenführungs Topologie, Seite "Edge-Setup" angeben] (images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistenten für die Zusammenführungs Topologie, Seite \"Edge-Setup\" angeben")  

5.  Geben Sie im Feld **Edge-Typ angeben**den Typ der Edgeserver-Konfiguration ein, und klicken Sie dann auf **weiter**. In diesem Beispiel wird die **Single Edge Server** -Option verwendet.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Erweiterte Edge-Bereitstellung</STRONG> ist keine unterstützte Konfiguration. Ein <STRONG>Erweiterter Edgeserver</STRONG> muss zuerst in einen <STRONG>einzelnen Edgeserver</STRONG> oder einen konsolidierten Edgeserver mit <STRONG>Lastenausgleich</STRONG> konvertiert werden.

    
    </div>

6.  Geben Sie unter Einstellungen für den **internen Rand angeben** die relevanten Informationen für den internen FQDN und die Ports Ihres Edge-Pools ein, und klicken Sie dann auf **weiter**.
    
    ![Dialogfeld ' Einstellungen für interne Kanten angeben '] (images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Dialogfeld ' Einstellungen für interne Kanten angeben '")  

7.  Geben Sie im Feld **externen Rand angeben**die FQDN-Informationen für Webkonferenzen für Ihren Edgeserver ein.
    
    <div>
    

    > [!IMPORTANT]  
    > Bevor Sie auf <STRONG>weiter</STRONG>klicken, führen Sie den nächsten Schritt in diesem Verfahren aus. Es ist sehr wichtig, dass Sie diesen Schritt nicht verpassen.

    
    </div>

8.  Aktivieren Sie das Kontrollkästchen **dieser Edge-Pool wird für Verbund-und öffentliche Chat Verbindungen verwendet** , wenn Sie beabsichtigen, den Legacy Office Communications Server 2007 R2-Edgeserver für den Verbund zu verwenden. Wenn Sie mehrere Edgeserver bereitgestellt haben, wird nur einer dieser Server für den Verbund aktiviert. Wenn Sie dieses Kontrollkästchen nicht aktivieren und später entscheiden, dass Sie den Verbund aktivieren möchten, müssen Sie den Zusammenführungs-Assistenten für Topologie-Generator ausführen und die Topologie erneut veröffentlichen.
    
    ![Dialogfeld ' Edgeserver ', Seite ' externe Kante angeben '] (images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Dialogfeld ' Edgeserver ', Seite ' externe Kante angeben '")  

9.  Geben Sie in **Nächster Hop angeben**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des nächsten Hop-Standorts in Ihrer Umgebung ein. Klicken Sie auf **Fertig stellen**.
    
    ![Dialogfeld ' Edgeserver ', Seite ' nächster Hop angeben '] (images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Dialogfeld ' Edgeserver ', Seite ' nächster Hop angeben '")  

10. Wenn alle Ihre Office Communications Server 2007 R2-Edgeserver hinzugefügt wurden, klicken Sie unter **Edge-Setup angeben**auf **weiter**. Wenn Sie weitere Office Communications Server 2007 R2-Edgeserver hinzufügen möchten, wiederholen Sie diesen Vorgang ab Schritt 4.

11. Wählen Sie unter **interner SIP-Port angeben** die Standardeinstellung aus (das heißt, wenn Sie den standardmäßigen SIP-Port nicht geändert haben). Ändern Sie die nach Bedarf, wenn Sie keinen Standardport von 5061 verwenden, und klicken Sie dann auf **weiter**.

12. Klicken Sie in **Zusammenfassung**auf **weiter** , um mit dem Zusammenführen der Topologien zu beginnen.

13. Die Seite des Assistenten überprüft, ob das Zusammenführen der Topologien erfolgreich war.

14. Überprüfen Sie in der Spalte **Status** , ob der Wert **erfolgreich**ist, und klicken Sie dann auf **Fertig stellen**.

15. Im linken Bereich des Topologie-Generators sollte nun der **BackCompatSite**angezeigt werden, der angibt, dass Ihre Office Communications Server 2007 R2-Umgebung mit lync Server 2013 zusammengeführt wurde.
    
    ![Topologie-Generator mit einer zusammengeführten Topologie] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topologie-Generator mit einer zusammengeführten Topologie")  

16. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und klicken Sie dann auf **weiter**.

17. Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen**.
    
    <div>
    

    > [!NOTE]  
    > Es ist wichtig, dass Sie das nächste Thema durchführen, <A href="import-policies-and-settings.md">Richtlinien und Einstellungen importieren</A>, um sicherzustellen, dass die Legacyrichtlinien Einstellungen in lync Server 2013 importiert werden.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

