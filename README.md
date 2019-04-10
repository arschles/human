# Logging in Go, For Humans

There are tons of log libraries out there for logging messages that machines can read. Here are a few off the top of my head:

- [glog](https://godoc.org/github.com/golang/glog)
- [zap](https://godoc.org/go.uber.org/zap)
- [klog](https://godoc.org/k8s.io/klog)
- [logutils](https://godoc.org/github.com/hashicorp/logutils)

Lots of these libraries actually do print out logs that humans can read, technically, but the logs don't look "nice". Sure, "nice" is subjective, but I'm talking about logs that don't include data in them that's meant for machines (i.e. "ugly" things), logs that can have colors (i.e. to represent different severities), and generally, logs that CLI tools can output.

This package is primarily meant for CLI tools to use when printing informational, warning and error messages, with colors!

I've rewritten code to do truly human-readable logs many times inside of CLI projects, and it usually ends up looking approximately the same. I decided to stop copy/pasting it from project to project and bring in the best code I've found to do these logs, from the [Helm project](https://github.com/helm/helm/blob/d87ce93e1e287ece84d940dbfe09b0de493d9953/pkg/kube/log.go).

`human` is a package heavily borrowed from the Helm project, with attribution and massive thanks.
