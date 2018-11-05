---
title: Erstellen oder Ändern einer neuen Regel für Clientversionsrichtlinien
TOCTitle: Erstellen oder Ändern einer neuen Regel für Clientversionsrichtlinien
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ898478(v=OCS.15)
ms:contentKeyID: 52056376
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer neuen Regel für Clientversionsrichtlinien

 

_**Letztes Änderungsdatum des Themas:** 2013-01-21_

Mit Regeln für Clientversionsrichtlinien werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten. Sie können einzelne Regeln für eine Clientversionsrichtlinie in der Systemsteuerung für Lync Server 2013 erstellen oder ändern.


> [!IMPORTANT]
> Regeln werden gemäß ihrer Rangfolge aufgelistet. Beispiel: Sie verfügen über eine Regel, die die Ausführung von Clientversion&nbsp;1.5 zulässt, gefolgt von einer Regel, die Clients mit früheren Versionen als Version&nbsp;2.0 blockiert. In diesem Fall hat die erste Regel Vorrang, und Clients mit Version&nbsp;1.5 können eine Verbindung herstellen.



## So erstellen oder ändern Sie Regeln für Clientversionsrichtlinien mithilfe der Lync Server-Systemsteuerung

1.  [Erstellen oder Ändern einer neuen Clientversionsrichtlinie](lync-server-2013-create-or-modify-a-new-client-version-policy.md) mit Lync Server-Systemsteuerung.

2.  Führen Sie auf der Seite **Clientversionsrichtlinie bearbeiten** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Neu**, um eine neue Clientversionsrichtlinie zu erstellen.
    
      - Klicken Sie auf einen der definierten Clienttypen in der Liste, und klicken Sie dann auf **Details einblenden**.
    

    > [!NOTE]
    > Sie können den Clienttyp mithilfe von Platzhalterzeichen angeben.



3.  Wählen Sie unter **Benutzer-Agent** einen Clienttyp aus.

4.  Führen Sie unter **Versionsnummer** die folgenden Aktionen aus:
    
      - Geben Sie in **Hauptversion** die Nummer ein, die der Hauptversion des Clients entspricht.
    
      - Geben Sie in **Nebenversion** die Nummer ein, die der Nebenversion des Clients entspricht.
    
      - Geben Sie in **Build** die Nummer ein, die der Haupt- und Nebenversion des Clients entspricht.
    
      - Geben Sie in **Update** die Nummer ein, die der aktualisierten Version des Clients entspricht.
    

    > [!NOTE]
    > Sie können die Clientversionsnummer mithilfe von Platzhalterzeichen angeben.



5.  Klicken Sie unter **Vergleichsvorgang** auf eine der folgenden Optionen, um den Vergleichsvorgang für die in den vorherigen Schritten angegebene Clientversion festzulegen:
    
      - **Gleich**
    
      - **Ungleich**
    
      - **Neuer als**
    
      - **Neuer als oder gleich**
    
      - **Älter als**
    
      - **Älter als oder gleich**

6.  Klicken Sie unter **Aktion** auf eine der folgenden Optionen, um die Aktion anzugeben, die bei Übereinstimmung mit dem angegebenen Kriterium ausgeführt werden soll:
    
      - Klicken Sie auf **Zulassen**, um die Anmeldung des Clients zu erlauben.
    
      - Klicken Sie auf **Zulassen und aktualisieren**, um dem Client die Anmeldung zu erlauben und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.
        

        > [!NOTE]
        > Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, sobald sich Benutzer das nächste Mal bei Lync 2013 anmelden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft&nbsp;Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.

    
      - Klicken Sie auf **Mit URL zulassen**, um die Anmeldung des Clients zu erlauben und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.
    
      - Um die Anmeldung des Clients zu verhindern, klicken Sie auf **Blockieren**.
    
      - Klicken Sie auf **Blockieren und aktualisieren**, um dem Client die Anmeldung zu verweigern und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.
    
      - Klicken Sie auf **Mit URL blockieren**, um die Anmeldung des Clients zu verweigern und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.

7.  (Optional) Wenn Sie im vorherigen Schritt auf **Mit URL zulassen** oder **Mit URL blockieren** geklickt haben, geben Sie unter **URL** die URL für den Clientdownload ein.

8.  Klicken Sie auf **OK** und dann auf **Commit ausführen**.

