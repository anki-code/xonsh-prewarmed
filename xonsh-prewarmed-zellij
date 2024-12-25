#!/bin/bash

get_reserve_sess_info() {
    zellij ls | grep "xonsh_sess_reserve" || true
}

reserve_sess_info=$(get_reserve_sess_info)

if [[ -z "$reserve_sess_info" ]]; then
    zellij -s xonsh_sess_reserve run -- xonsh -DXONSH_PREWARMED=1
fi

zellij attach -c xonsh_sess_reserve
zellij action rename-session "xonsh_sess_active"

zellij -s xonsh_sess_reserve run -- xonsh -DXONSH_PREWARMED=1
