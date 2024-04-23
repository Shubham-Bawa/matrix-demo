![][1]

 {#section .ListParagraph}

 {#section-1 .ListParagraph}

Contents {#contents .TOCHeading}
========

[Exercise: Installing K8s and 3]

[Prerequisite 3]

[Scenario: **In this activity, we will cover how to install crossplane.** 3]

 {#section-2 .ListParagraph}

 {#section-3 .ListParagraph}

 {#section-4 .ListParagraph}

 {#section-5 .ListParagraph}

 {#section-6 .ListParagraph}

 {#section-7 .ListParagraph}

 {#section-8 .ListParagraph}

 {#section-9 .ListParagraph}

 {#section-10 .ListParagraph}

 {#section-11 .ListParagraph}

 {#section-12 .ListParagraph}

  **Version**   **Revision Date**   **Description**   **Author(s)**   **Reviewed by**   **Approved by**
  ------------- ------------------- ----------------- --------------- ----------------- -----------------
                                                                                        
                                                                                        
                                                                                         

 {#section-13 .ListParagraph}

Exercise: Installing K8s and  {#exercise-installing-k8s-and .ListParagraph}
=============================

Prerequisite {#prerequisite .ListParagraph}
------------

Scenario: In this activity, we will cover how to install crossplane. {#scenario-in-this-activity-we-will-cover-how-to-install-crossplane. .ListParagraph}
--------------------------------------------------------------------

+------------+---------------------------------------------------------------------------------------------------------------------+
| **Step 1** | Install Docker engine on the vm by using this command: -                                                            |
|            |                                                                                                                     |
|            | sudo su -\                                                                                                          |
|            | \                                                                                                                   |
|            | curl -fsSL http://get.docker.**com** \| **sh**                                                                      |
|            |                                                                                                                     |
|            | ![][2]                                                                                                              |
|            |                                                                                                                     |
|            | This command is install all the  [Dependencies]                                                                     |
|            |                                                                                                                     |
|            | Start the docker services using this command.                                                                       |
|            |                                                                                                                     |
|            | systemctl start docker                                                                                              |
|            |                                                                                                                     |
|            | check the status for the docker.                                                                                    |
|            |                                                                                                                     |
|            | Run this command.                                                                                                   |
|            |                                                                                                                     |
|            | **systemctl status docker**                                                                                         |
|            |                                                                                                                     |
|            | ![][3]                                                                                                              |
+============+=====================================================================================================================+
| **Step 2** | Install the Kubectl                                                                                                 |
|            |                                                                                                                     |
|            | Download Kubectl using curl command.                                                                                |
|            |                                                                                                                     |
|            | curl -LO https://dl.k8s.io/release/\$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl      |
|            |                                                                                                                     |
|            | Install using install command.                                                                                      |
|            |                                                                                                                     |
|            | sudo **install** -o root -g root -m 0755 kubectl /usr/**bin**/kubectl                                               |
+------------+---------------------------------------------------------------------------------------------------------------------+
| **Step 3** | Install kind                                                                                                        |
|            |                                                                                                                     |
|            | Kind is an open-source tool for running a Kubernetes cluster locally, using Docker containers as cluster nodes.     |
|            |                                                                                                                     |
|            | Download the kind                                                                                                   |
|            |                                                                                                                     |
|            | curl -Lo ./kind \"https://kind.sigs.k8s.io/dl/v0.11.1/kind-\$(uname)-amd64\"                                        |
|            |                                                                                                                     |
|            | chmod +x ./**kind**\                                                                                                |
|            | \                                                                                                                   |
|            | sudo mv ./**kind** /usr/bin/**kind**                                                                                |
|            |                                                                                                                     |
|            | Install Kubernetes with kind                                                                                        |
|            |                                                                                                                     |
|            | sudo kind **create** **cluster**                                                                                    |
|            |                                                                                                                     |
|            | ![][4]                                                                                                              |
|            |                                                                                                                     |
|            | Run the command. To verify the Kubernetes nodes                                                                     |
|            |                                                                                                                     |
|            | Kubectl get nodes                                                                                                   |
|            |                                                                                                                     |
|            | ![][5]                                                                                                              |
+------------+---------------------------------------------------------------------------------------------------------------------+
| **Step 4** | Turn on the Cross-plane Helm Chart database:                                                                        |
|            |                                                                                                                     |
|            | helm repo **add** crossplane-**stable** https://charts.crossplane.io/**stable**                                     |
|            |                                                                                                                     |
|            | **helm repo update**                                                                                                |
+------------+---------------------------------------------------------------------------------------------------------------------+
| **Step 5** | Install Helm Chart for cross-plane.                                                                                 |
|            |                                                                                                                     |
|            | helm install crossplane crossplane-stable/crossplane \--**namespace** crossplane-**system** \--create-**namespace** |
+------------+---------------------------------------------------------------------------------------------------------------------+
| **Step 6** | **Verify Crossplane-pods **                                                                                         |
|            |                                                                                                                     |
|            | kubectl get pods -n crossplane-**system**                                                                           |
|            |                                                                                                                     |
|            | You will have output like this: -                                                                                   |
|            |                                                                                                                     |
|            | NAME READY STATUS RESTARTS AGE                                                                                      |
|            |                                                                                                                     |
|            | crossplane-d4cd8d784-b 1/1 Running 0 60s                                                                            |
|            |                                                                                                                     |
|            | crossplane-rbac-manager-847 1/1 Running 0                                                                           |
+------------+---------------------------------------------------------------------------------------------------------------------+

Copyright © 2024 Accenture

All rights reserved.

Accenture and its logo are trademarks of Accenture.

![][6]

  [1]: media/image1.png {width="3.004166666666667in" height="3.115972222222222in"}
  [Exercise: Installing K8s and 3]: #exercise-installing-k8s-and
  [Prerequisite 3]: #prerequisite
  [Scenario: **In this activity, we will cover how to install crossplane.** 3]: #scenario-in-this-activity-we-will-cover-how-to-install-crossplane.
  [2]: media/image2.png {width="5.547916666666667in" height="0.45902777777777776in"}
  [Dependencies]: https://www.google.com/search?sca_esv=561856720&rlz=1C1GCEA_enIN1056IN1056&sxsrf=AB5stBidc9vp-2_DE_xAEs80jyhT7SMRgg:1693550317545&q=Dependencies&spell=1&sa=X&ved=2ahUKEwjAnNjI5oiBAxVRHnAKHR_nDD8QkeECKAB6BAgMEAE
  [3]: media/image3.png {width="5.547916666666667in" height="1.198611111111111in"}
  [4]: media/image4.png {width="5.547916666666667in" height="1.6576388888888889in"}
  [5]: media/image5.png {width="5.342129265091864in" height="0.43337051618547684in"}
  [6]: media/image6.png {width="1.37in" height="1.5in"}
