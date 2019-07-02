[![Build Status](https://travis-ci.org/cfn-modules/fargate-service.svg?branch=master)](https://travis-ci.org/cfn-modules/fargate-service)
[![NPM version](https://img.shields.io/npm/v/@cfn-modules/fargate-service.svg)](https://www.npmjs.com/package/@cfn-modules/fargate-service)

# cfn-modules: Fargate service

Fargate service.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/fargate-service
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Service:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        VpcModule: !GetAtt 'Vpc.Outputs.StackName' # required
        ClusterModule: !GetAtt 'Cluster.Outputs.StackName' # optional
        TargetModule: '' # optional
        AlertingModule: '' # optional
        ClientSgModule1: '' # optional
        ClientSgModule2: '' # optional
        ClientSgModule3: '' # optional
        ManagedPolicyArns: '' # optional
        ProxyImage: '' # optional
        ProxyPort: '8000' # optional
        ProxyEnvironment01: '' # optional
        ProxyEnvironment02: '' # optional
        ProxyEnvironment03: '' # optional
        AppImage: 'widdix/hello:v1' # optional
        AppPort: '80' # optional
        AppEnvironment01: '' # optional
        AppEnvironment02: '' # optional
        AppEnvironment03: '' # optional
        AppEnvironment04: '' # optional
        AppEnvironment05: '' # optional
        AppEnvironment06: '' # optional
        AppEnvironment07: '' # optional
        AppEnvironment08: '' # optional
        AppEnvironment09: '' # optional
        AppEnvironment10: '' # optional
        AppEnvironment11: '' # optional
        AppEnvironment12: '' # optional
        AppEnvironment13: '' # optional
        AppEnvironment14: '' # optional
        AppEnvironment15: '' # optional
        AppEnvironment16: '' # optional
        AppEnvironment17: '' # optional
        AppEnvironment18: '' # optional
        AppEnvironment19: '' # optional
        AppEnvironment20: '' # optional
        AppEnvironment21: '' # optional
        AppEnvironment22: '' # optional
        AppEnvironment23: '' # optional
        AppEnvironment24: '' # optional
        AppEnvironment25: '' # optional
        AppEnvironment26: '' # optional
        AppEnvironment27: '' # optional
        AppEnvironment28: '' # optional
        AppEnvironment29: '' # optional
        AppEnvironment30: '' # optional
        SidecarImage: '' # optional
        SidecarPort: '9000' # optional
        SidecarEnvironment01: '' # optional
        SidecarEnvironment02: '' # optional
        SidecarEnvironment03: '' # optional
        Cpu: '0.25' # optional
        Memory: '0.5' # optional
        DesiredCount: '2' # optional
        MaxCapacity: '4' # optional
        MinCapacity: '2' # optional
        LogsRetentionInDays: '14' # optional
        SubnetsReach: 'Public' # optional
        AutoScaling: 'true' # optional
        HealthCheckGracePeriodSeconds: '60' # optional
      TemplateURL: './node_modules/@cfn-modules/fargate-service/module.yml'
```

## Examples

* [fargate-alb-proxy-pattern](https://github.com/cfn-modules/docs/tree/master/examples/fargate-alb-proxy-pattern)
* [fargate-alb-single-container](https://github.com/cfn-modules/docs/tree/master/examples/fargate-alb-single-container)

## Related modules

* [alb](https://github.com/cfn-modules/alb)
* [nlb](https://github.com/cfn-modules/nlb)

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>VpcModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/vpc">vpc module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>ClusterModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/ecs-cluster">ecs-cluster module</a> (if empty, an ECS cluster is created)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>TargetModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/search?q=keywords:cfn-modules:Target">module implementing Target</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AlertingModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/alerting">alerting module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ClientSgModule1</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/client-sg">client-sg module</a> module to mark traffic from EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ClientSgModule2</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/client-sg">client-sg module</a> module to mark traffic from EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ClientSgModule3</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/client-sg">client-sg module</a> module to mark traffic from EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ManagedPolicyArns</td>
      <td>Comma-delimited list of IAM managed policy ARNs to attach to the task's IAM role</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ProxyImage</td>
      <td>Docker image to use for the proxy container. You can use images in the Docker Hub registry or specify other repositories (repository-url/image:tag)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ProxyPort</td>
      <td>The port exposed by the proxy container that receives traffic from the load balancer (ProxyPort != AppPort != SidecarPort; ignored if ProxyImage and/or TargetModule are/is not set)</td>
      <td>8000</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ProxyEnvironment01</td>
      <td>Environment variable 01 for proxy container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ProxyEnvironment02</td>
      <td>Environment variable 02 for proxy container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ProxyEnvironment03</td>
      <td>Environment variable 03 for proxy container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppImage</td>
      <td>The Docker image to use for the app container. You can use images in the Docker Hub registry or specify other repositories (repository-url/image:tag)</td>
      <td>widdix/hello:v1</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppPort</td>
      <td>The port exposed by the app container that receives traffic from the load balancer or the proxy container (AppPort != ProxyPort != SidecarPort; ignored if TargetModule is not set)</td>
      <td>80</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment01</td>
      <td>Environment variable 01 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment02</td>
      <td>Environment variable 02 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment03</td>
      <td>Environment variable 03 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment04</td>
      <td>Environment variable 04 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment05</td>
      <td>Environment variable 05 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment06</td>
      <td>Environment variable 06 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment07</td>
      <td>Environment variable 07 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment08</td>
      <td>Environment variable 08 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment09</td>
      <td>Environment variable 09 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment10</td>
      <td>Environment variable 10 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment11</td>
      <td>Environment variable 11 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment12</td>
      <td>Environment variable 12 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment13</td>
      <td>Environment variable 13 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment14</td>
      <td>Environment variable 14 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment15</td>
      <td>Environment variable 15 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment16</td>
      <td>Environment variable 16 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment17</td>
      <td>Environment variable 17 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment18</td>
      <td>Environment variable 18 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment19</td>
      <td>Environment variable 19 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment20</td>
      <td>Environment variable 20 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment21</td>
      <td>Environment variable 21 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment22</td>
      <td>Environment variable 22 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment23</td>
      <td>Environment variable 23 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment24</td>
      <td>Environment variable 24 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment25</td>
      <td>Environment variable 25 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment26</td>
      <td>Environment variable 26 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment27</td>
      <td>Environment variable 27 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment28</td>
      <td>Environment variable 28 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment29</td>
      <td>Environment variable 29 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment30</td>
      <td>Environment variable 30 for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarImage</td>
      <td>Docker image to use for the sidecar container. You can use images in the Docker Hub registry or specify other repositories (repository-url/image:tag)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarPort</td>
      <td>The port exposed by the sidecar container reachable from the app container on host localhost (SidecarPort != ProxyPort != AppPort)</td>
      <td>9000</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment01</td>
      <td>Environment variable 01 for sidecar container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment02</td>
      <td>Environment variable 02 for sidecar container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment03</td>
      <td>Environment variable 03 for sidecar container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>Cpu</td>
      <td>The minimum number of vCPUs to reserve for the container</td>
      <td>0.25</td>
      <td>no</td>
      <td>[0.25, 0.5, 1, 2, 4]</td>
    </tr>
    <tr>
      <td>Memory</td>
      <td>The amount (in GB) of memory used by the task</td>
      <td>0.5</td>
      <td>no</td>
      <td>[0.5, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30]</td>
    </tr>
    <tr>
      <td>DesiredCount</td>
      <td>The number of simultaneous tasks, that you want to run on the cluster</td>
      <td>2</td>
      <td>no</td>
      <td>1-N</td>
    </tr>
    <tr>
      <td>MaxCapacity</td>
      <td>The maximum number of simultaneous tasks, that you want to run on the cluster</td>
      <td>4</td>
      <td>no</td>
      <td>1-N</td>
    </tr>
    <tr>
      <td>MinCapacity</td>
      <td>The minimum number of simultaneous tasks, that you want to run on the cluster</td>
      <td>2</td>
      <td>no</td>
      <td>1-N</td>
    </tr>
    <tr>
      <td>LogsRetentionInDays</td>
      <td>Specifies the number of days you want to retain log events in the specified log group</td>
      <td>14</td>
      <td>no</td>
      <td>[1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653]</td>
    </tr>
    <tr>
      <td>SubnetsReach</td>
      <td>Should the service have direct access to the Internet or do you prefer private subnets with NAT?</td>
      <td>Public</td>
      <td>no</td>
      <td>[Public, Private]</td>
    </tr>
    <tr>
      <td>AutoScaling</td>
      <td>Scale number of tasks based on CPU load?</td>
      <td>true</td>
      <td>no</td>
      <td>[true, false]</td>
    </tr>
    <tr>
      <td>HealthCheckGracePeriodSeconds</td>
      <td>The period of time, in seconds, that the Amazon ECS service scheduler ignores unhealthy Elastic Load Balancing target health checks after a task has first started (ignored if TargetModule is not set)</td>
      <td>60</td>
      <td>no</td>
      <td>0-1800</td>
    </tr>
  </tbody>
</table>

## Migration Guides

### Migrate to v2

* Rename `AmbassadorImage` to `ProxyImage`.
* Rename `AmbassadorPort` to `ProxyPort`.
* Rename `AmbassadorEnvironment1Key` to `ProxyEnvironment1Key`.
* Rename `AmbassadorEnvironment1Value` to `ProxyEnvironment1Value`.
* Rename `AmbassadorEnvironment2Key` to `ProxyEnvironment2Key`.
* Rename `AmbassadorEnvironment2Value` to `ProxyEnvironment2Value`.
* Rename `AmbassadorEnvironment3Key` to `ProxyEnvironment3Key`.
* Rename `AmbassadorEnvironment3Value` to `ProxyEnvironment3Value`.
