#!/bin/bash
pods=$(kubectl get pods -n ${params.Namespace} | grep ${params.Replicaset} | awk '{print $1}')
m=0
for pods in $pods
do
  ((m++)
  kubectl delete pod $pod -n ${params.Namespace}
  if [[$m -eq $n]]; then
      break
  fi
done
