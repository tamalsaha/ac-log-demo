# ac-log-demo

## Demo Projects

- https://github.com/tamalsaha/std-log-demo
- https://github.com/tamalsaha/glog-demo
- https://github.com/tamalsaha/kube-log-demo
- https://github.com/tamalsaha/ac-log-demo

```console
$ ac-log-demo check -h
Check restic backup

Usage:
   check [flags]

Flags:
  -h, --help                help for check
      --kubeconfig string   Path to kubeconfig file with authorization information (the master location is set by the master flag).
      --master string       The address of the Kubernetes API server (overrides any value in kubeconfig)

Global Flags:
      --alsologtostderr                  log to standard error as well as files
      --analytics                        Send analytical events to Google Analytics (default true)
      --log_backtrace_at traceLocation   when logging hits line file:N, emit a stack trace (default :0)
      --log_dir string                   If non-empty, write log files in this directory
      --logtostderr                      log to standard error instead of files (default true)
      --stderrthreshold severity         logs at or above this threshold go to stderr (default 2)
  -v, --v Level                          log level for V logs
      --vmodule moduleSpec               comma-separated list of pattern=N settings for file-filtered logging

$ ac-log-demo check
W0108 18:54:12.328504   22932 client_config.go:529] Neither --kubeconfig nor --master was specified.  Using the inClusterConfig.  This might not work.
W0108 18:54:12.328847   22932 client_config.go:534] error creating inClusterConfig, falling back to default config: unable to load in-cluster configuration, KUBERNETES_SERVICE_HOST and KUBERNETES_SERVICE_PORT must be defined
F0108 18:54:12.329110   22932 main.go:53] invalid configuration: no configuration has been provided

$ ac-log-demo check --kubeconfig=/home/tamal/.kube/config
glog.Infoln_____
I0108 18:54:40.307631   23041 main.go:64] minikube
glog.Warningln_____
W0108 18:54:40.307701   23041 main.go:67] minikube
glog.Errorln_____
E0108 18:54:40.307711   23041 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:54:40.307720   23041 main.go:75] minikube
glog.V(1).Infoln_____
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ ac-log-demo check --kubeconfig=/home/tamal/.kube/config --v=2
glog.Infoln_____
I0108 18:54:56.229513   23093 main.go:64] minikube
glog.Warningln_____
W0108 18:54:56.229665   23093 main.go:67] minikube
glog.Errorln_____
E0108 18:54:56.229683   23093 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:54:56.229702   23093 main.go:75] minikube
glog.V(1).Infoln_____
I0108 18:54:56.229720   23093 main.go:78] minikube
glog.V(2).Infoln_____
I0108 18:54:56.229737   23093 main.go:81] minikube
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ ac-log-demo check --kubeconfig=/home/tamal/.kube/config --v=2 --logtostderr=true
glog.Infoln_____
I0108 18:55:08.377678   23169 main.go:64] minikube
glog.Warningln_____
W0108 18:55:08.377843   23169 main.go:67] minikube
glog.Errorln_____
E0108 18:55:08.377869   23169 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:55:08.377891   23169 main.go:75] minikube
glog.V(1).Infoln_____
I0108 18:55:08.377913   23169 main.go:78] minikube
glog.V(2).Infoln_____
I0108 18:55:08.377937   23169 main.go:81] minikube
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ ac-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true
glog.Infoln_____
I0108 18:55:16.438773   23203 main.go:64] minikube
glog.Warningln_____
W0108 18:55:16.438871   23203 main.go:67] minikube
glog.Errorln_____
E0108 18:55:16.438940   23203 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:55:16.438982   23203 main.go:75] minikube
glog.V(1).Infoln_____
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

 ac-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true --stderrthreshold=1
glog.Infoln_____
I0108 18:55:28.170375   23289 main.go:64] minikube
glog.Warningln_____
W0108 18:55:28.170463   23289 main.go:67] minikube
glog.Errorln_____
E0108 18:55:28.170478   23289 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:55:28.170493   23289 main.go:75] minikube
glog.V(1).Infoln_____
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ ac-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true --stderrthreshold=1 --v=1
glog.Infoln_____
I0108 18:55:36.194675   23327 main.go:64] minikube
glog.Warningln_____
W0108 18:55:36.195183   23327 main.go:67] minikube
glog.Errorln_____
E0108 18:55:36.195466   23327 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:55:36.195490   23327 main.go:75] minikube
glog.V(1).Infoln_____
I0108 18:55:36.195509   23327 main.go:78] minikube
glog.V(2).Infoln_____
glog.V(3).Infoln_____
glog.V(4).Infoln_____

$ ac-log-demo check --kubeconfig=/home/tamal/.kube/config --logtostderr=true --stderrthreshold=1 --v=2
glog.Infoln_____
I0108 18:55:38.632408   23366 main.go:64] minikube
glog.Warningln_____
W0108 18:55:38.632547   23366 main.go:67] minikube
glog.Errorln_____
E0108 18:55:38.632578   23366 main.go:70] minikube
glog.V(0).Infoln_____
I0108 18:55:38.632598   23366 main.go:75] minikube
glog.V(1).Infoln_____
I0108 18:55:38.632616   23366 main.go:78] minikube
glog.V(2).Infoln_____
I0108 18:55:38.632634   23366 main.go:81] minikube
glog.V(3).Infoln_____
glog.V(4).Infoln_____
```