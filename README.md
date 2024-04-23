![](images/media/image1.png)

## 

## 

# Contents

[Exercise: Installing K8s and 3](#exercise-installing-k8s-and)

[Prerequisite 3](#prerequisite)

[Scenario: **In this activity, we will cover how to install crossplane.** 3](#scenario-in-this-activity-we-will-cover-how-to-install-crossplane.)

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 

| **Version** | **Revision Date** | **Description** | **Author(s)** | **Reviewed by** | **Approved by** |
| ----------- | ----------------- | --------------- | ------------- | --------------- | --------------- |
|             |                   |                 |               |                 |                 |
|             |                   |                 |               |                 |                 |
|             |                   |                 |               |                 |                 |

## 

# Exercise: Installing K8s and 

## Prerequisite

## Scenario: In this activity, we will cover how to install crossplane.

<table>
<thead>
<tr class="header">
<th><strong>Step 1</strong></th>
<th><p>Install Docker engine on the vm by using this command: -</p>
<p>sudo su -<br />
<br />
curl -fsSL http://get.docker.<strong>com</strong> | <strong>sh</strong></p>
<p><img src="images/media/image2.png" style="width:5.54792in;height:0.45903in" /></p>
<p>This command is install all the  <a href="https://www.google.com/search?sca_esv=561856720&amp;rlz=1C1GCEA_enIN1056IN1056&amp;sxsrf=AB5stBidc9vp-2_DE_xAEs80jyhT7SMRgg:1693550317545&amp;q=Dependencies&amp;spell=1&amp;sa=X&amp;ved=2ahUKEwjAnNjI5oiBAxVRHnAKHR_nDD8QkeECKAB6BAgMEAE">Dependencies</a></p>
<p>Start the docker services using this command.</p>
<p>systemctl start docker</p>
<p>check the status for the docker.</p>
<p>Run this command.</p>
<p><strong>systemctl status docker</strong></p>
<p><img src="images/media/image3.png" style="width:5.54792in;height:1.19861in" /></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Step 2</strong></td>
<td><p>Install the Kubectl</p>
<p>Download Kubectl using curl command.</p>
<p>curl -LO https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl</p>
<p>Install using install command.</p>
<p>sudo <strong>install</strong> -o root -g root -m 0755 kubectl /usr/<strong>bin</strong>/kubectl</p></td>
</tr>
<tr class="even">
<td><strong>Step 3</strong></td>
<td><p>Install kind</p>
<p>Kind is an open-source tool for running a Kubernetes cluster locally, using Docker containers as cluster nodes.</p>
<p>Download the kind</p>
<p>curl -Lo ./kind "https://kind.sigs.k8s.io/dl/v0.11.1/kind-$(uname)-amd64"</p>
<p>chmod +x ./<strong>kind</strong><br />
<br />
sudo mv ./<strong>kind</strong> /usr/bin/<strong>kind</strong></p>
<p>Install Kubernetes with kind</p>
<p>sudo kind <strong>create</strong> <strong>cluster</strong></p>
<p><img src="images/media/image4.png" style="width:5.54792in;height:1.65764in" /></p>
<p>Run the command. To verify the Kubernetes nodes</p>
<p>Kubectl get nodes</p>
<p><img src="images/media/image5.png" style="width:5.34213in;height:0.43337in" /></p></td>
</tr>
<tr class="odd">
<td><strong>Step 4</strong></td>
<td><p>Turn on the Cross-plane Helm Chart database:</p>
<p>helm repo <strong>add</strong> crossplane-<strong>stable</strong> https://charts.crossplane.io/<strong>stable</strong></p>
<p><strong>helm repo update</strong></p></td>
</tr>
<tr class="even">
<td><strong>Step 5</strong></td>
<td><p>Install Helm Chart for cross-plane.</p>
<p>helm install crossplane crossplane-stable/crossplane --<strong>namespace</strong> crossplane-<strong>system</strong> --create-<strong>namespace</strong></p></td>
</tr>
<tr class="odd">
<td><strong>Step 6</strong></td>
<td><p><strong>Verify Crossplane-pods </strong></p>
<p>kubectl get pods -n crossplane-<strong>system</strong></p>
<p>You will have output like this: -</p>
<p>NAME READY STATUS RESTARTS AGE</p>
<p>crossplane-d4cd8d784-b 1/1 Running 0 60s</p>
<p>crossplane-rbac-manager-847 1/1 Running 0</p></td>
</tr>
</tbody>
</table>

Copyright © 2024 Accenture

All rights reserved.

Accenture and its logo are trademarks of Accenture.

![](images/media/image6.png)
