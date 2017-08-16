# Stories
Arrows
! function(e) {
    “use strict”;

    function t(e, t) {
        return t = t || Error,
            function() {
                var n, i, r = 2,
                    o = arguments,
                    a = o[0],
                    s = “[” + (e ? e + “:” : “”) + a + “] “,
                    l = o[1];
                for (s += l.replace(/\{\d+\}/g, function(e) {
                        var t = +e.slice(1, -1),
                            n = t + r;
                        return n < o.length ? be(o[n]) : e
                    }), s += “\nhttp://errors.angularjs.org/1.5.8/” + (e ? e + “/” : “”) + a, i = r, n = “?”; i < o.length; i++, n = “&”) s += n + “p” + (i - r) + “=” + encodeURIComponent(be(o[i]));
                return new t(s)
            }
    }

    function n(e) {
        if (null == e || D(e)) return !1;
        if (Ki(e) || w(e) || Ri && e instanceof Ri) return !0;
        var t = “length” in Object(e) && e.length;
        return x(t) && (t >= 0 && (t - 1 in e || e instanceof Array) || “function” == typeof e.item)
    }

    function i(e, t, r) {
        var o, a;
        if (e)
            if (C(e))
                for (o in e) “prototype” == o || “length” == o || “name” == o || e.hasOwnProperty && !e.hasOwnProperty(o) || t.call(r, e[o], o, e);
            else if (Ki(e) || n(e)) {
            var s = “object” != typeof e;
            for (o = 0, a = e.length; o < a; o++)(s || o in e) && t.call(r, e[o], o, e)
        } else if (e.forEach && e.forEach !== i) e.forEach(t, r, e);
        else if (y(e))
            for (o in e) t.call(r, e[o], o, e);
        else if (“function” == typeof e.hasOwnProperty)
            for (o in e) e.hasOwnProperty(o) && t.call(r, e[o], o, e);
        else
            for (o in e) Oi.call(e, o) && t.call(r, e[o], o, e);
        return e
    }

    function r(e, t, n) {
        for (var i = Object.keys(e).sort(), r = 0; r < i.length; r++) t.call(n, e[i[r]], i[r]);
        return i
    }

    function o(e) {
        return function(t, n) {
            e(n, t)
        }
    }

    function a() {
        return ++Yi
    }

    function s(e, t) {
        t ? e.$$hashKey = t : delete e.$$hashKey
    }

    function l(e, t, n) {
        for (var i = e.$$hashKey, r = 0, o = t.length; r < o; ++r) {
            var a = t[r];
            if ($(a) || C(a))
                for (var u = Object.keys(a), c = 0, d = u.length; c < d; c++) {
                    var p = u[c],
                        f = a[p];
                    n && $(f) ? T(f) ? e[p] = new Date(f.valueOf()) : k(f) ? e[p] = new RegExp(f) : f.nodeName ? e[p] = f.cloneNode(!0) : L(f) ? e[p] = f.clone() : ($(e[p]) || (e[p] = Ki(f) ? [] : {}), l(e[p], [f], !0)) : e[p] = f
                }
        }
        return s(e, i), e
    }

    function u(e) {
        return l(e, Ui.call(arguments, 1), !1)
    }

    function c(e) {
        return l(e, Ui.call(arguments, 1), !0)
    }

    function d(e) {
        return parseInt(e, 10)
    }

    function p(e, t) {
        return u(Object.create(e), t)
    }

    function f() {}

    function m(e) {
        return e
    }

    function g(e) {
        return function() {
            return e
        }
    }

    function h(e) {
        return C(e.toString) && e.toString !== Hi
    }

    function v(e) {
        return “undefined” == typeof e
    }

    function b(e) {
        return “undefined” != typeof e
    }

    function $(e) {
        return null !== e && “object” == typeof e
    }

    function y(e) {
        return null !== e && “object” == typeof e && !Gi(e)
    }

    function w(e) {
        return “string” == typeof e
    }

    function x(e) {
        return “number” == typeof e
    }

    function T(e) {
        return “[object Date]” === Hi.call(e)
    }

    function C(e) {
        return “function” == typeof e
    }

    function k(e) {
        return “[object RegExp]” === Hi.call(e)
    }

    function D(e) {
        return e && e.window === e
    }

    function _(e) {
        return e && e.$evalAsync && e.$watch
    }

    function S(e) {
        return “[object File]” === Hi.call(e)
    }

    function M(e) {
        return “[object FormData]” === Hi.call(e)
    }

    function A(e) {
        return “[object Blob]” === Hi.call(e)
    }

    function P(e) {
        return “boolean” == typeof e
    }

    function O(e) {
        return e && C(e.then)
    }

    function E(e) {
        return e && x(e.length) && Zi.test(Hi.call(e))
    }

    function I(e) {
        return “[object ArrayBuffer]” === Hi.call(e)
    }

    function L(e) {
        return !(!e || !(e.nodeName || e.prop && e.attr && e.find))
    }

    function q(e) {
        var t, n = {},
            i = e.split(“,”);
        for (t = 0; t < i.length; t++) n[i[t]] = !0;
        return n
    }

    function F(e) {
        return Ei(e.nodeName || e[0] && e[0].nodeName)
    }

    function R(e, t) {
        var n = e.indexOf(t);
        return n >= 0 && e.splice(n, 1), n
    }

    function V(e, t) {
        function n(e, t) {
            var n, i = t.$$hashKey;
            if (Ki(e))
                for (var o = 0, a = e.length; o < a; o++) t.push(r(e[o]));
            else if (y(e))
                for (n in e) t[n] = r(e[n]);
            else if (e && “function” == typeof e.hasOwnProperty)
                for (n in e) e.hasOwnProperty(n) && (t[n] = r(e[n]));
            else
                for (n in e) Oi.call(e, n) && (t[n] = r(e[n]));
            return s(t, i), t
        }

        function r(e) {
            if (!$(e)) return e;
            var t = a.indexOf(e);
            if (t !== -1) return l[t];
            if (D(e) || _(e)) throw zi(“cpws”, “Can’t copy! Making copies of Window or Scope instances is not supported.“);
            var i = !1,
                r = o(e);
            return void 0 === r && (r = Ki(e) ? [] : Object.create(Gi(e)), i = !0), a.push(e), l.push(r), i ? n(e, r) : r
        }

        function o(e) {
            switch (Hi.call(e)) {
                case “[object Int8Array]“:
                case “[object Int16Array]“:
                case “[object Int32Array]“:
                case “[object Float32Array]“:
                case “[object Float64Array]“:
                case “[object Uint8Array]“:
                case “[object Uint8ClampedArray]“:
                case “[object Uint16Array]“:
                case “[object Uint32Array]“:
                    return new e.constructor(r(e.buffer), e.byteOffset, e.length);
                case “[object ArrayBuffer]“:
                    if (!e.slice) {
                        var t = new ArrayBuffer(e.byteLength);
                        return new Uint8Array(t).set(new Uint8Array(e)), t
                    }
                    return e.slice(0);
                case “[object Boolean]“:
                case “[object Number]“:
                case “[object String]“:
                case “[object Date]“:
                    return new e.constructor(e.valueOf());
                case “[object RegExp]“:
                    var n = new RegExp(e.source, e.toString().match(/[^\/]*$/)[0]);
                    return n.lastIndex = e.lastIndex, n;
                case “[object Blob]“:
                    return new e.constructor([e], {
                        type: e.type
                    })
            }
            if (C(e.cloneNode)) return e.cloneNode(!0)
        }
        var a = [],
            l = [];
        if (t) {
            if (E(t) || I(t)) throw zi(“cpta”, “Can’t copy! TypedArray destination cannot be mutated.“);
            if (e === t) throw zi(“cpi”, “Can’t copy! Source and destination are identical.“);
            return Ki(t) ? t.length = 0 : i(t, function(e, n) {
                “$$hashKey” !== n && delete t[n]
            }), a.push(e), l.push(t), n(e, t)
        }
        return r(e)
    }

    function N(e, t) {
        if (e === t) return !0;
        if (null === e || null === t) return !1;
        if (e !== e && t !== t) return !0;
        var n, i, r, o = typeof e,
            a = typeof t;
        if (o == a && “object” == o) {
            if (!Ki(e)) {
                if (T(e)) return !!T(t) && N(e.getTime(), t.getTime());
                if (k(e)) return !!k(t) && e.toString() == t.toString();
                if (_(e) || _(t) || D(e) || D(t) || Ki(t) || T(t) || k(t)) return !1;
                r = me();
                for (i in e)
                    if (“$” !== i.charAt(0) && !C(e[i])) {
                        if (!N(e[i], t[i])) return !1;
                        r[i] = !0
                    }
                for (i in t)
                    if (!(i in r) && “$” !== i.charAt(0) && b(t[i]) && !C(t[i])) return !1;
                return !0
            }
            if (!Ki(t)) return !1;
            if ((n = e.length) == t.length) {
                for (i = 0; i < n; i++)
                    if (!N(e[i], t[i])) return !1;
                return !0
            }
        }
        return !1
    }

    function U(e, t, n) {
        return e.concat(Ui.call(t, n))
    }

    function j(e, t) {
        return Ui.call(e, t || 0)
    }

    function B(e, t) {
        var n = arguments.length > 2 ? j(arguments, 2) : [];
        return !C(t) || t instanceof RegExp ? t : n.length ? function() {
            return arguments.length ? t.apply(e, U(n, arguments, 0)) : t.apply(e, n)
        } : function() {
            return arguments.length ? t.apply(e, arguments) : t.call(e)
        }
    }

    function H(t, n) {
        var i = n;
        return “string” == typeof t && “$” === t.charAt(0) && “$” === t.charAt(1) ? i = void 0 : D(n) ? i = “$WINDOW” : n && e.document === n ? i = “$DOCUMENT” : _(n) && (i = “$SCOPE”), i
    }

    function G(e, t) {
        if (!v(e)) return x(t) || (t = t ? 2 : null), JSON.stringify(e, H, t)
    }

    function z(e) {
        return w(e) ? JSON.parse(e) : e
    }

    function W(e, t) {
        e = e.replace(tr, “”);
        var n = Date.parse(“Jan 01, 1970 00:00:00 ” + e) / 6e4;
        return isNaN(n) ? t : n
    }

    function Y(e, t) {
        return e = new Date(e.getTime()), e.setMinutes(e.getMinutes() + t), e
    }

    function K(e, t, n) {
        n = n ? -1 : 1;
        var i = e.getTimezoneOffset(),
            r = W(t, i);
        return Y(e, n * (r - i))
    }

    function Z(e) {
        e = Ri(e).clone();
        try {
            e.empty()
        } catch (e) {}
        var t = Ri(“<div>“).append(e).html();
        try {
            return e[0].nodeType === sr ? Ei(t) : t.match(/^(<[^>]+>)/)[1].replace(/^<([\w\-]+)/, function(e, t) {
                return “<” + Ei(t)
            })
        } catch (e) {
            return Ei(t)
        }
    }

    function X(e) {
        try {
            return decodeURIComponent(e)
        } catch (e) {}
    }

    function J(e) {
        var t = {};
        return i((e || “”).split(“&”), function(e) {
            var n, i, r;
            e && (i = e = e.replace(/\+/g, “%20"), n = e.indexOf(“=”), n !== -1 && (i = e.substring(0, n), r = e.substring(n + 1)), i = X(i), b(i) && (r = !b(r) || X(r), Oi.call(t, i) ? Ki(t[i]) ? t[i].push(r) : t[i] = [t[i], r] : t[i] = r))
        }), t
    }

    function Q(e) {
        var t = [];
        return i(e, function(e, n) {
            Ki(e) ? i(e, function(e) {
                t.push(te(n, !0) + (e === !0 ? “” : “=” + te(e, !0)))
            }) : t.push(te(n, !0) + (e === !0 ? “” : “=” + te(e, !0)))
        }), t.length ? t.join(“&”) : “”
    }

    function ee(e) {
        return te(e, !0).replace(/%26/gi, “&”).replace(/%3D/gi, “=”).replace(/%2B/gi, “+”)
    }

    function te(e, t) {
        return encodeURIComponent(e).replace(/%40/gi, “@”).replace(/%3A/gi, “:”).replace(/%24/g, “$”).replace(/%2C/gi, “,”).replace(/%3B/gi, “;”).replace(/%20/g, t ? “%20" : “+”)
    }

    function ne(e, t) {
        var n, i, r = nr.length;
        for (i = 0; i < r; ++i)
            if (n = nr[i] + t, w(n = e.getAttribute(n))) return n;
        return null
    }

    function ie(e, t) {
        var n, r, o = {};
        i(nr, function(t) {
            var i = t + “app”;
            !n && e.hasAttribute && e.hasAttribute(i) && (n = e, r = e.getAttribute(i))
        }), i(nr, function(t) {
            var i, o = t + “app”;
            !n && (i = e.querySelector(“[” + o.replace(“:”, “\\:“) + “]”)) && (n = i, r = i.getAttribute(o))
        }), n && (o.strictDi = null !== ne(n, “strict-di”), t(n, r ? [r] : [], o))
    }

    function re(t, n, r) {
        $(r) || (r = {});
        var o = {
            strictDi: !1
        };
        r = u(o, r);
        var a = function() {
                if (t = Ri(t), t.injector()) {
                    var i = t[0] === e.document ? “document” : Z(t);
                    throw zi(“btstrpd”, “App already bootstrapped with this element ‘{0}‘“, i.replace(/</, “&lt;“).replace(/>/, “&gt;“))
                }
                n = n || [], n.unshift([“$provide”, function(e) {
                    e.value(“$rootElement”, t)
                }]), r.debugInfoEnabled && n.push([“$compileProvider”, function(e) {
                    e.debugInfoEnabled(!0)
                }]), n.unshift(“ng”);
                var o = it(n, r.strictDi);
                return o.invoke([“$rootScope”, “$rootElement”, “$compile”, “$injector”, function(e, t, n, i) {
                    e.$apply(function() {
                        t.data(“$injector”, i), n(t)(e)
                    })
                }]), o
            },
            s = /^NG_ENABLE_DEBUG_INFO!/,
            l = /^NG_DEFER_BOOTSTRAP!/;
        return e && s.test(e.name) && (r.debugInfoEnabled = !0, e.name = e.name.replace(s, “”)), e && !l.test(e.name) ? a() : (e.name = e.name.replace(l, “”), Wi.resumeBootstrap = function(e) {
            return i(e, function(e) {
                n.push(e)
            }), a()
        }, void(C(Wi.resumeDeferredBootstrap) && Wi.resumeDeferredBootstrap()))
    }

    function oe() {
        e.name = “NG_ENABLE_DEBUG_INFO!” + e.name, e.location.reload()
    }

    function ae(e) {
        var t = Wi.element(e).injector();
        if (!t) throw zi(“test”, “no injector found for element argument to getTestability”);
        return t.get(“$$testability”)
    }

    function se(e, t) {
        return t = t || “_”, e.replace(ir, function(e, n) {
            return (n ? t : “”) + e.toLowerCase()
        })
    }

    function le() {
        var t;
        if (!rr) {
            var n = er();
            Vi = v(n) ? e.jQuery : n ? e[n] : void 0, Vi && Vi.fn.on ? (Ri = Vi, u(Vi.fn, {
                scope: Dr.scope,
                isolateScope: Dr.isolateScope,
                controller: Dr.controller,
                injector: Dr.injector,
                inheritedData: Dr.inheritedData
            }), t = Vi.cleanData, Vi.cleanData = function(e) {
                for (var n, i, r = 0; null != (i = e[r]); r++) n = Vi._data(i, “events”), n && n.$destroy && Vi(i).triggerHandler(“$destroy”);
                t(e)
            }) : Ri = Me, Wi.element = Ri, rr = !0
        }
    }

    function ue(e, t, n) {
        if (!e) throw zi(“areq”, “Argument ‘{0}’ is {1}“, t || “?”, n || “required”);
        return e
    }

    function ce(e, t, n) {
        return n && Ki(e) && (e = e[e.length - 1]), ue(C(e), t, “not a function, got ” + (e && “object” == typeof e ? e.constructor.name || “Object” : typeof e)), e
    }

    function de(e, t) {
        if (“hasOwnProperty” === e) throw zi(“badname”, “hasOwnProperty is not a valid {0} name”, t)
    }

    function pe(e, t, n) {
        if (!t) return e;
        for (var i, r = t.split(“.”), o = e, a = r.length, s = 0; s < a; s++) i = r[s], e && (e = (o = e)[i]);
        return !n && C(e) ? B(o, e) : e
    }

    function fe(e) {
        for (var t, n = e[0], i = e[e.length - 1], r = 1; n !== i && (n = n.nextSibling); r++)(t || e[r] !== n) && (t || (t = Ri(Ui.call(e, 0, r))), t.push(n));
        return t || e
    }

    function me() {
        return Object.create(null)
    }

    function ge(e) {
        function n(e, t, n) {
            return e[t] || (e[t] = n())
        }
        var i = t(“$injector”),
            r = t(“ng”),
            o = n(e, “angular”, Object);
        return o.$$minErr = o.$$minErr || t, n(o, “module”, function() {
            var e = {};
            return function(t, o, a) {
                var s = function(e, t) {
                    if (“hasOwnProperty” === e) throw r(“badname”, “hasOwnProperty is not a valid {0} name”, t)
                };
                return s(t, “module”), o && e.hasOwnProperty(t) && (e[t] = null), n(e, t, function() {
                    function e(e, t, n, i) {
                        return i || (i = r),
                            function() {
                                return i[n || “push”]([e, t, arguments]), c
                            }
                    }

                    function n(e, n) {
                        return function(i, o) {
                            return o && C(o) && (o.$$moduleName = t), r.push([e, n, arguments]), c
                        }
                    }
                    if (!o) throw i(“nomod”, “Module ‘{0}’ is not available! You either misspelled the module name or forgot to load it. If registering a module ensure that you specify the dependencies as the second argument.“, t);
                    var r = [],
                        s = [],
                        l = [],
                        u = e(“$injector”, “invoke”, “push”, s),
                        c = {
                            _invokeQueue: r,
                            _configBlocks: s,
                            _runBlocks: l,
                            requires: o,
                            name: t,
                            provider: n(“$provide”, “provider”),
                            factory: n(“$provide”, “factory”),
                            service: n(“$provide”, “service”),
                            value: e(“$provide”, “value”),
                            constant: e(“$provide”, “constant”, “unshift”),
                            decorator: n(“$provide”, “decorator”),
                            animation: n(“$animateProvider”, “register”),
                            filter: n(“$filterProvider”, “register”),
                            controller: n(“$controllerProvider”, “register”),
                            directive: n(“$compileProvider”, “directive”),
                            component: n(“$compileProvider”, “component”),
                            config: u,
                            run: function(e) {
                                return l.push(e), this
                            }
                        };
                    return a && u(a), c
                })
            }
        })
    }

    function he(e, t) {
        if (Ki(e)) {
            t = t || [];
            for (var n = 0, i = e.length; n < i; n++) t[n] = e[n]
        } else if ($(e)) {
            t = t || {};
            for (var r in e) “$” === r.charAt(0) && “$” === r.charAt(1) || (t[r] = e[r])
        }
        return t || e
    }

    function ve(e) {
        var t = [];
        return JSON.stringify(e, function(e, n) {
            if (n = H(e, n), $(n)) {
                if (t.indexOf(n) >= 0) return “...“;
                t.push(n)
            }
            return n
        })
    }

    function be(e) {
        return “function” == typeof e ? e.toString().replace(/ \{[\s\S]*$/, “”) : v(e) ? “undefined” : “string” != typeof e ? ve(e) : e
    }

    function $e(n) {
        u(n, {
            bootstrap: re,
            copy: V,
            extend: u,
            merge: c,
            equals: N,
            element: Ri,
            forEach: i,
            injector: it,
            noop: f,
            bind: B,
            toJson: G,
            fromJson: z,
            identity: m,
            isUndefined: v,
            isDefined: b,
            isString: w,
            isFunction: C,
            isObject: $,
            isNumber: x,
            isElement: L,
            isArray: Ki,
            version: dr,
            isDate: T,
            lowercase: Ei,
            uppercase: Ii,
            callbacks: {
                $$counter: 0
            },
            getTestability: ae,
            $$minErr: t,
            $$csp: Qi,
            reloadWithDebugInfo: oe
        }), (Ni = ge(e))(“ng”, [“ngLocale”], [“$provide”, function(e) {
            e.provider({
                $$sanitizeUri: kn
            }), e.provider(“$compile”, mt).directive({
                a: Lo,
                input: ea,
                textarea: ea,
                form: No,
                script: Ka,
                select: Ja,
                style: es,
                option: Qa,
                ngBind: ia,
                ngBindHtml: oa,
                ngBindTemplate: ra,
                ngClass: sa,
                ngClassEven: ua,
                ngClassOdd: la,
                ngCloak: ca,
                ngController: da,
                ngForm: Uo,
                ngHide: ja,
                ngIf: ma,
                ngInclude: ga,
                ngInit: va,
                ngNonBindable: Ea,
                ngPluralize: Fa,
                ngRepeat: Ra,
                ngShow: Ua,
                ngStyle: Ba,
                ngSwitch: Ha,
                ngSwitchWhen: Ga,
                ngSwitchDefault: za,
                ngOptions: qa,
                ngTransclude: Ya,
                ngModel: Aa,
                ngList: ba,
                ngChange: aa,
                pattern: ns,
                ngPattern: ns,
                required: ts,
                ngRequired: ts,
                minlength: rs,
                ngMinlength: rs,
                maxlength: is,
                ngMaxlength: is,
                ngValue: na,
                ngModelOptions: Oa
            }).directive({
                ngInclude: ha
            }).directive(qo).directive(pa), e.provider({
                $anchorScroll: rt,
                $animate: jr,
                $animateCss: Gr,
                $$animateJs: Nr,
                $$animateQueue: Ur,
                $$AnimateRunner: Hr,
                $$animateAsyncRun: Br,
                $browser: ct,
                $cacheFactory: dt,
                $controller: yt,
                $document: wt,
                $exceptionHandler: xt,
                $filter: Vn,
                $$forceReflow: Xr,
                $interpolate: qt,
                $interval: Ft,
                $http: Ot,
                $httpParamSerializer: Ct,
                $httpParamSerializerJQLike: kt,
                $httpBackend: It,
                $xhrFactory: Et,
                $jsonpCallbacks: ao,
                $location: Jt,
                $log: Qt,
                $parse: $n,
                $rootScope: Cn,
                $q: yn,
                $$q: wn,
                $sce: Mn,
                $sceDelegate: Sn,
                $sniffer: An,
                $templateCache: pt,
                $templateRequest: Pn,
                $$testability: On,
                $timeout: En,
                $window: qn,
                $$rAF: Tn,
                $$jqLite: Ze,
                $$HashMap: Ar,
                $$cookieReader: Rn
            })
        }])
    }

    function ye() {
        return ++fr
    }

    function we(e) {
        return e.replace(hr, function(e, t, n, i) {
            return i ? n.toUpperCase() : n
        }).replace(vr, “Moz$1”)
    }

    function xe(e) {
        return !wr.test(e)
    }

    function Te(e) {
        var t = e.nodeType;
        return t === or || !t || t === ur
    }

    function Ce(e) {
        for (var t in pr[e.ng339]) return !0;
        return !1
    }

    function ke(e) {
        for (var t = 0, n = e.length; t < n; t++) Ee(e[t])
    }

    function De(e, t) {
        var n, r, o, a, s = t.createDocumentFragment(),
            l = [];
        if (xe(e)) l.push(t.createTextNode(e));
        else {
            for (n = s.appendChild(t.createElement(“div”)), r = (xr.exec(e) || [“”, “”])[1].toLowerCase(), o = Cr[r] || Cr._default, n.innerHTML = o[1] + e.replace(Tr, “<$1></$2>“) + o[2], a = o[0]; a--;) n = n.lastChild;
            l = U(l, n.childNodes), n = s.firstChild, n.textContent = “”
        }
        return s.textContent = “”, s.innerHTML = “”, i(l, function(e) {
            s.appendChild(e)
        }), s
    }

    function _e(t, n) {
        n = n || e.document;
        var i;
        return (i = yr.exec(t)) ? [n.createElement(i[1])] : (i = De(t, n)) ? i.childNodes : []
    }

    function Se(e, t) {
        var n = e.parentNode;
        n && n.replaceChild(t, e), t.appendChild(e)
    }

    function Me(e) {
        if (e instanceof Me) return e;
        var t;
        if (w(e) && (e = Xi(e), t = !0), !(this instanceof Me)) {
            if (t && “<” != e.charAt(0)) throw $r(“nosel”, “Looking up elements via selectors is not supported by jqLite! See: http://docs.angularjs.org/api/angular.element”);
            return new Me(e)
        }
        t ? Ve(this, _e(e)) : Ve(this, e)
    }

    function Ae(e) {
        return e.cloneNode(!0)
    }

    function Pe(e, t) {
        if (t || Ee(e), e.querySelectorAll)
            for (var n = e.querySelectorAll(“*”), i = 0, r = n.length; i < r; i++) Ee(n[i])
    }

    function Oe(e, t, n, r) {
        if (b(r)) throw $r(“offargs”, “jqLite#off() does not support the `selector` argument”);
        var o = Ie(e),
            a = o && o.events,
            s = o && o.handle;
        if (s)
            if (t) {
                var l = function(t) {
                    var i = a[t];
                    b(n) && R(i || [], n), b(n) && i && i.length > 0 || (gr(e, t, s), delete a[t])
                };
                i(t.split(” “), function(e) {
                    l(e), br[e] && l(br[e])
                })
            } else
                for (t in a) “$destroy” !== t && gr(e, t, s), delete a[t]
    }

    function Ee(e, t) {
        var n = e.ng339,
            i = n && pr[n];
        if (i) {
            if (t) return void delete i.data[t];
            i.handle && (i.events.$destroy && i.handle({}, “$destroy”), Oe(e)), delete pr[n], e.ng339 = void 0
        }
    }

    function Ie(e, t) {
        var n = e.ng339,
            i = n && pr[n];
        return t && !i && (e.ng339 = n = ye(), i = pr[n] = {
            events: {},
            data: {},
            handle: void 0
        }), i
    }

    function Le(e, t, n) {
        if (Te(e)) {
            var i = b(n),
                r = !i && t && !$(t),
                o = !t,
                a = Ie(e, !r),
                s = a && a.data;
            if (i) s[t] = n;
            else {
                if (o) return s;
                if (r) return s && s[t];
                u(s, t)
            }
        }
    }

    function qe(e, t) {
        return !!e.getAttribute && (” ” + (e.getAttribute(“class”) || “”) + ” “).replace(/[\n\t]/g, ” “).indexOf(” ” + t + ” “) > -1
    }

    function Fe(e, t) {
        t && e.setAttribute && i(t.split(” “), function(t) {
            e.setAttribute(“class”, Xi((” ” + (e.getAttribute(“class”) || “”) + ” “).replace(/[\n\t]/g, ” “).replace(” ” + Xi(t) + ” “, ” “)))
        })
    }

    function Re(e, t) {
        if (t && e.setAttribute) {
            var n = (” ” + (e.getAttribute(“class”) || “”) + ” “).replace(/[\n\t]/g, ” “);
            i(t.split(” “), function(e) {
                e = Xi(e), n.indexOf(” ” + e + ” “) === -1 && (n += e + ” “)
            }), e.setAttribute(“class”, Xi(n))
        }
    }

    function Ve(e, t) {
        if (t)
            if (t.nodeType) e[e.length++] = t;
            else {
                var n = t.length;
                if (“number” == typeof n && t.window !== t) {
                    if (n)
                        for (var i = 0; i < n; i++) e[e.length++] = t[i]
                } else e[e.length++] = t
            }
    }

    function Ne(e, t) {
        return Ue(e, “$” + (t || “ngController”) + “Controller”)
    }

    function Ue(e, t, n) {
        e.nodeType == ur && (e = e.documentElement);
        for (var i = Ki(t) ? t : [t]; e;) {
            for (var r = 0, o = i.length; r < o; r++)
                if (b(n = Ri.data(e, i[r]))) return n;
            e = e.parentNode || e.nodeType === cr && e.host
        }
    }

    function je(e) {
        for (Pe(e, !0); e.firstChild;) e.removeChild(e.firstChild)
    }

    function Be(e, t) {
        t || Pe(e);
        var n = e.parentNode;
        n && n.removeChild(e)
    }

    function He(t, n) {
        n = n || e, “complete” === n.document.readyState ? n.setTimeout(t) : Ri(n).on(“load”, t)
    }

    function Ge(e, t) {
        var n = _r[t.toLowerCase()];
        return n && Sr[F(e)] && n
    }

    function ze(e) {
        return Mr[e]
    }

    function We(e, t) {
        var n = function(n, i) {
            n.isDefaultPrevented = function() {
                return n.defaultPrevented
            };
            var r = t[i || n.type],
                o = r ? r.length : 0;
            if (o) {
                if (v(n.immediatePropagationStopped)) {
                    var a = n.stopImmediatePropagation;
                    n.stopImmediatePropagation = function() {
                        n.immediatePropagationStopped = !0, n.stopPropagation && n.stopPropagation(), a && a.call(n)
                    }
                }
                n.isImmediatePropagationStopped = function() {
                    return n.immediatePropagationStopped === !0
                };
                var s = r.specialHandlerWrapper || Ye;
                o > 1 && (r = he(r));
                for (var l = 0; l < o; l++) n.isImmediatePropagationStopped() || s(e, n, r[l])
            }
        };
        return n.elem = e, n
    }

    function Ye(e, t, n) {
        n.call(e, t)
    }

    function Ke(e, t, n) {
        var i = t.relatedTarget;
        i && (i === e || kr.call(e, i)) || n.call(e, t)
    }

    function Ze() {
        this.$get = function() {
            return u(Me, {
                hasClass: function(e, t) {
                    return e.attr && (e = e[0]), qe(e, t)
                },
                addClass: function(e, t) {
                    return e.attr && (e = e[0]), Re(e, t)
                },
                removeClass: function(e, t) {
                    return e.attr && (e = e[0]), Fe(e, t)
                }
            })
        }
    }

    function Xe(e, t) {
        var n = e && e.$$hashKey;
        if (n) return “function” == typeof n && (n = e.$$hashKey()), n;
        var i = typeof e;
        return n = “function” == i || “object” == i && null !== e ? e.$$hashKey = i + “:” + (t || a)() : i + “:” + e
    }

    function Je(e, t) {
        if (t) {
            var n = 0;
            this.nextUid = function() {
                return ++n
            }
        }
        i(e, this.put, this)
    }

    function Qe(e) {
        return Function.prototype.toString.call(e) + ” ”
    }

    function et(e) {
        var t = Qe(e).replace(Lr, “”),
            n = t.match(Pr) || t.match(Or);
        return n
    }

    function tt(e) {
        var t = et(e);
        return t ? “function(” + (t[1] || “”).replace(/[\s\r\n]+/, ” “) + “)” : “fn”
    }

    function nt(e, t, n) {
        var r, o, a;
        if (“function” == typeof e) {
            if (!(r = e.$inject)) {
                if (r = [], e.length) {
                    if (t) throw w(n) && n || (n = e.name || tt(e)), qr(“strictdi”, “{0} is not using explicit annotation and cannot be invoked in strict mode”, n);
                    o = et(e), i(o[1].split(Er), function(e) {
                        e.replace(Ir, function(e, t, n) {
                            r.push(n)
                        })
                    })
                }
                e.$inject = r
            }
        } else Ki(e) ? (a = e.length - 1, ce(e[a], “fn”), r = e.slice(0, a)) : ce(e, “fn”, !0);
        return r
    }

    function it(e, t) {
        function n(e) {
            return function(t, n) {
                return $(t) ? void i(t, o(e)) : e(t, n)
            }
        }

        function r(e, t) {
            if (de(e, “service”), (C(t) || Ki(t)) && (t = T.instantiate(t)), !t.$get) throw qr(“pget”, “Provider ‘{0}’ must define $get factory method.“, e);
            return x[e + h] = t
        }

        function a(e, t) {
            return function() {
                var n = _.invoke(t, this);
                if (v(n)) throw qr(“undef”, “Provider ‘{0}’ must return a value from $get factory method.“, e);
                return n
            }
        }

        function s(e, t, n) {
            return r(e, {
                $get: n !== !1 ? a(e, t) : t
            })
        }

        function l(e, t) {
            return s(e, [“$injector”, function(e) {
                return e.instantiate(t)
            }])
        }

        function u(e, t) {
            return s(e, g(t), !1)
        }

        function c(e, t) {
            de(e, “constant”), x[e] = t, k[e] = t
        }

        function d(e, t) {
            var n = T.get(e + h),
                i = n.$get;
            n.$get = function() {
                var e = _.invoke(i, n);
                return _.invoke(t, null, {
                    $delegate: e
                })
            }
        }

        function p(e) {
            ue(v(e) || Ki(e), “modulesToLoad”, “not an array”);
            var t, n = [];
            return i(e, function(e) {
                function i(e) {
                    var t, n;
                    for (t = 0, n = e.length; t < n; t++) {
                        var i = e[t],
                            r = T.get(i[0]);
                        r[i[1]].apply(r, i[2])
                    }
                }
                if (!y.get(e)) {
                    y.put(e, !0);
                    try {
                        w(e) ? (t = Ni(e), n = n.concat(p(t.requires)).concat(t._runBlocks), i(t._invokeQueue), i(t._configBlocks)) : C(e) ? n.push(T.invoke(e)) : Ki(e) ? n.push(T.invoke(e)) : ce(e, “module”)
                    } catch (t) {
                        throw Ki(e) && (e = e[e.length - 1]), t.message && t.stack && t.stack.indexOf(t.message) == -1 && (t = t.message + “\n” + t.stack), qr(“modulerr”, “Failed to instantiate module {0} due to:\n{1}“, e, t.stack || t.message || t)
                    }
                }
            }), n
        }

        function f(e, n) {
            function i(t, i) {
                if (e.hasOwnProperty(t)) {
                    if (e[t] === m) throw qr(“cdep”, “Circular dependency found: {0}“, t + ” <- ” + b.join(” <- “));
                    return e[t]
                }
                try {
                    return b.unshift(t), e[t] = m, e[t] = n(t, i)
                } catch (n) {
                    throw e[t] === m && delete e[t], n
                } finally {
                    b.shift()
                }
            }

            function r(e, n, r) {
                for (var o = [], a = it.$$annotate(e, t, r), s = 0, l = a.length; s < l; s++) {
                    var u = a[s];
                    if (“string” != typeof u) throw qr(“itkn”, “Incorrect injection token! Expected service name as string, got {0}“, u);
                    o.push(n && n.hasOwnProperty(u) ? n[u] : i(u, r))
                }
                return o
            }

            function o(e) {
                return !(Fi <= 11) && (“function” == typeof e && /^(?:class\b|constructor\()/.test(Qe(e)))
            }

            function a(e, t, n, i) {
                “string” == typeof n && (i = n, n = null);
                var a = r(e, n, i);
                return Ki(e) && (e = e[e.length - 1]), o(e) ? (a.unshift(null), new(Function.prototype.bind.apply(e, a))) : e.apply(t, a)
            }

            function s(e, t, n) {
                var i = Ki(e) ? e[e.length - 1] : e,
                    o = r(e, t, n);
                return o.unshift(null), new(Function.prototype.bind.apply(i, o))
            }
            return {
                invoke: a,
                instantiate: s,
                get: i,
                annotate: it.$$annotate,
                has: function(t) {
                    return x.hasOwnProperty(t + h) || e.hasOwnProperty(t)
                }
            }
        }
        t = t === !0;
        var m = {},
            h = “Provider”,
            b = [],
            y = new Je([], (!0)),
            x = {
                $provide: {
                    provider: n(r),
                    factory: n(s),
                    service: n(l),
                    value: n(u),
                    constant: n(c),
                    decorator: d
                }
            },
            T = x.$injector = f(x, function(e, t) {
                throw Wi.isString(t) && b.push(t), qr(“unpr”, “Unknown provider: {0}“, b.join(” <- “))
            }),
            k = {},
            D = f(k, function(e, t) {
                var n = T.get(e + h, t);
                return _.invoke(n.$get, n, void 0, e)
            }),
            _ = D;
        x[“$injector” + h] = {
            $get: g(D)
        };
        var S = p(e);
        return _ = D.get(“$injector”), _.strictDi = t, i(S, function(e) {
            e && _.invoke(e)
        }), _
    }

    function rt() {
        var e = !0;
        this.disableAutoScrolling = function() {
            e = !1
        }, this.$get = [“$window”, “$location”, “$rootScope”, function(t, n, i) {
            function r(e) {
                var t = null;
                return Array.prototype.some.call(e, function(e) {
                    if (“a” === F(e)) return t = e, !0
                }), t
            }

            function o() {
                var e = s.yOffset;
                if (C(e)) e = e();
                else if (L(e)) {
                    var n = e[0],
                        i = t.getComputedStyle(n);
                    e = “fixed” !== i.position ? 0 : n.getBoundingClientRect().bottom
                } else x(e) || (e = 0);
                return e
            }

            function a(e) {
                if (e) {
                    e.scrollIntoView();
                    var n = o();
                    if (n) {
                        var i = e.getBoundingClientRect().top;
                        t.scrollBy(0, i - n)
                    }
                } else t.scrollTo(0, 0)
            }

            function s(e) {
                e = w(e) ? e : n.hash();
                var t;
                e ? (t = l.getElementById(e)) ? a(t) : (t = r(l.getElementsByName(e))) ? a(t) : “top” === e && a(null) : a(null)
            }
            var l = t.document;
            return e && i.$watch(function() {
                return n.hash()
            }, function(e, t) {
                e === t && “” === e || He(function() {
                    i.$evalAsync(s)
                })
            }), s
        }]
    }

    function ot(e, t) {
        return e || t ? e ? t ? (Ki(e) && (e = e.join(” “)), Ki(t) && (t = t.join(” “)), e + ” ” + t) : e : t : “”
    }

    function at(e) {
        for (var t = 0; t < e.length; t++) {
            var n = e[t];
            if (n.nodeType === Rr) return n
        }
    }

    function st(e) {
        w(e) && (e = e.split(” “));
        var t = me();
        return i(e, function(e) {
            e.length && (t[e] = !0)
        }), t
    }

    function lt(e) {
        return $(e) ? e : {}
    }

    function ut(e, t, n, r) {
        function o(e) {
            try {
                e.apply(null, j(arguments, 1))
            } finally {
                if (b--, 0 === b)
                    for (; $.length;) try {
                        $.pop()()
                    } catch (e) {
                        n.error(e)
                    }
            }
        }

        function a(e) {
            var t = e.indexOf(“#”);
            return t === -1 ? “” : e.substr(t)
        }

        function s() {
            C = null, l(), u()
        }

        function l() {
            y = k(), y = v(y) ? null : y, N(y, S) && (y = S), S = y
        }

        function u() {
            x === c.url() && w === y || (x = c.url(), w = y, i(D, function(e) {
                e(c.url(), y)
            }))
        }
        var c = this,
            d = e.location,
            p = e.history,
            m = e.setTimeout,
            g = e.clearTimeout,
            h = {};
        c.isMock = !1;
        var b = 0,
            $ = [];
        c.$$completeOutstandingRequest = o, c.$$incOutstandingRequestCount = function() {
            b++
        }, c.notifyWhenNoOutstandingRequests = function(e) {
            0 === b ? e() : $.push(e)
        };
        var y, w, x = d.href,
            T = t.find(“base”),
            C = null,
            k = r.history ? function() {
                try {
                    return p.state
                } catch (e) {}
            } : f;
        l(), w = y, c.url = function(t, n, i) {
            if (v(i) && (i = null), d !== e.location && (d = e.location), p !== e.history && (p = e.history), t) {
                var o = w === i;
                if (x === t && (!r.history || o)) return c;
                var s = x && Bt(x) === Bt(t);
                return x = t, w = i, !r.history || s && o ? (s || (C = t), n ? d.replace(t) : s ? d.hash = a(t) : d.href = t, d.href !== t && (C = t)) : (p[n ? “replaceState” : “pushState”](i, “”, t), l(), w = y), C && (C = t), c
            }
            return C || d.href.replace(/%27/g, “‘”)
        }, c.state = function() {
            return y
        };
        var D = [],
            _ = !1,
            S = null;
        c.onUrlChange = function(t) {
            return _ || (r.history && Ri(e).on(“popstate”, s), Ri(e).on(“hashchange”, s), _ = !0), D.push(t), t
        }, c.$$applicationDestroyed = function() {
            Ri(e).off(“hashchange popstate”, s)
        }, c.$$checkUrlChange = u, c.baseHref = function() {
            var e = T.attr(“href”);
            return e ? e.replace(/^(https?\:)?\/\/[^\/]*/, “”) : “”
        }, c.defer = function(e, t) {
            var n;
            return b++, n = m(function() {
                delete h[n], o(e)
            }, t || 0), h[n] = !0, n
        }, c.defer.cancel = function(e) {
            return !!h[e] && (delete h[e], g(e), o(f), !0)
        }
    }

    function ct() {
        this.$get = [“$window”, “$log”, “$sniffer”, “$document”, function(e, t, n, i) {
            return new ut(e, i, t, n)
        }]
    }

    function dt() {
        this.$get = function() {
            function e(e, i) {
                function r(e) {
                    e != p && (f ? f == e && (f = e.n) : f = e, o(e.n, e.p), o(e, p), p = e, p.n = null)
                }

                function o(e, t) {
                    e != t && (e && (e.p = t), t && (t.n = e))
                }
                if (e in n) throw t(“$cacheFactory”)(“iid”, “CacheId ‘{0}’ is already taken!“, e);
                var a = 0,
                    s = u({}, i, {
                        id: e
                    }),
                    l = me(),
                    c = i && i.capacity || Number.MAX_VALUE,
                    d = me(),
                    p = null,
                    f = null;
                return n[e] = {
                    put: function(e, t) {
                        if (!v(t)) {
                            if (c < Number.MAX_VALUE) {
                                var n = d[e] || (d[e] = {
                                    key: e
                                });
                                r(n)
                            }
                            return e in l || a++, l[e] = t, a > c && this.remove(f.key), t
                        }
                    },
                    get: function(e) {
                        if (c < Number.MAX_VALUE) {
                            var t = d[e];
                            if (!t) return;
                            r(t)
                        }
                        return l[e]
                    },
                    remove: function(e) {
                        if (c < Number.MAX_VALUE) {
                            var t = d[e];
                            if (!t) return;
                            t == p && (p = t.p), t == f && (f = t.n), o(t.n, t.p), delete d[e]
                        }
                        e in l && (delete l[e], a--)
                    },
                    removeAll: function() {
                        l = me(), a = 0, d = me(), p = f = null
                    },
                    destroy: function() {
                        l = null, s = null, d = null, delete n[e]
                    },
                    info: function() {
                        return u({}, s, {
                            size: a
                        })
                    }
                }
            }
            var n = {};
            return e.info = function() {
                var e = {};
                return i(n, function(t, n) {
                    e[n] = t.info()
                }), e
            }, e.get = function(e) {
                return n[e]
            }, e
        }
    }

    function pt() {
        this.$get = [“$cacheFactory”, function(e) {
            return e(“templates”)
        }]
    }

    function ft() {}

    function mt(t, n) {
        function r(e, t, n) {
            var r = /^\s*([@&<]|=(\*?))(\??)\s*(\w*)\s*$/,
                o = me();
            return i(e, function(e, i) {
                if (e in D) return void(o[i] = D[e]);
                var a = e.match(r);
                if (!a) throw zr(“iscp”, “Invalid {3} for directive ‘{0}‘. Definition: {... {1}: ‘{2}’ ...}“, t, i, e, n ? “controller bindings definition” : “isolate scope definition”);
                o[i] = {
                    mode: a[1][0],
                    collection: “*” === a[2],
                    optional: “?” === a[3],
                    attrName: a[4] || i
                }, a[4] && (D[e] = o[i])
            }), o
        }

        function a(e, t) {
            var n = {
                isolateScope: null,
                bindToController: null
            };
            if ($(e.scope) && (e.bindToController === !0 ? (n.bindToController = r(e.scope, t, !0), n.isolateScope = {}) : n.isolateScope = r(e.scope, t, !1)), $(e.bindToController) && (n.bindToController = r(e.bindToController, t, !0)), $(n.bindToController)) {
                var i = e.controller,
                    o = e.controllerAs;
                if (!i) throw zr(“noctrl”, “Cannot bind to controller without directive ‘{0}‘s controller.“, t);
                if (!$t(i, o)) throw zr(“noident”, “Cannot bind to controller without identifier for directive ‘{0}‘.“, t)
            }
            return n
        }

        function s(e) {
            var t = e.charAt(0);
            if (!t || t !== Ei(t)) throw zr(“baddir”, “Directive/Component name ‘{0}’ is invalid. The first character must be a lowercase letter”, e);
            if (e !== e.trim()) throw zr(“baddir”, “Directive/Component name ‘{0}’ is invalid. The name should not contain leading or trailing whitespaces”, e)
        }

        function l(e) {
            var t = e.require || e.controller && e.name;
            return !Ki(t) && $(t) && i(t, function(e, n) {
                var i = e.match(T),
                    r = e.substring(i[0].length);
                r || (t[n] = i[0] + n)
            }), t
        }
        var c = {},
            d = “Directive”,
            h = /^\s*directive\:\s*([\w\-]+)\s+(.*)$/,
            y = /(([\w\-]+)(?:\:([^;]+))?;?)/,
            x = q(“ngSrc,ngSrcset,src,srcset”),
            T = /^(?:(\^\^?)?(\?)?(\^\^?)?)?/,
            k = /^(on[a-z]+|formaction)$/,
            D = me();
        this.directive = function e(n, r) {
            return de(n, “directive”), w(n) ? (s(n), ue(r, “directiveFactory”), c.hasOwnProperty(n) || (c[n] = [], t.factory(n + d, [“$injector”, “$exceptionHandler”, function(e, t) {
                var r = [];
                return i(c[n], function(i, o) {
                    try {
                        var a = e.invoke(i);
                        C(a) ? a = {
                            compile: g(a)
                        } : !a.compile && a.link && (a.compile = g(a.link)), a.priority = a.priority || 0, a.index = o, a.name = a.name || n, a.require = l(a), a.restrict = a.restrict || “EA”, a.$$moduleName = i.$$moduleName, r.push(a)
                    } catch (e) {
                        t(e)
                    }
                }), r
            }])), c[n].push(r)) : i(n, o(e)), this
        }, this.component = function(e, t) {
            function n(e) {
                function n(t) {
                    return C(t) || Ki(t) ? function(n, i) {
                        return e.invoke(t, this, {
                            $element: n,
                            $attrs: i
                        })
                    } : t
                }
                var o = t.template || t.templateUrl ? t.template : “”,
                    a = {
                        controller: r,
                        controllerAs: $t(t.controller) || t.controllerAs || “$ctrl”,
                        template: n(o),
                        templateUrl: n(t.templateUrl),
                        transclude: t.transclude,
                        scope: {},
                        bindToController: t.bindings || {},
                        restrict: “E”,
                        require: t.require
                    };
                return i(t, function(e, t) {
                    “$” === t.charAt(0) && (a[t] = e)
                }), a
            }
            var r = t.controller || function() {};
            return i(t, function(e, t) {
                “$” === t.charAt(0) && (n[t] = e, C(r) && (r[t] = e))
            }), n.$inject = [“$injector”], this.directive(e, n)
        }, this.aHrefSanitizationWhitelist = function(e) {
            return b(e) ? (n.aHrefSanitizationWhitelist(e), this) : n.aHrefSanitizationWhitelist()
        }, this.imgSrcSanitizationWhitelist = function(e) {
            return b(e) ? (n.imgSrcSanitizationWhitelist(e), this) : n.imgSrcSanitizationWhitelist()
        };
        var S = !0;
        this.debugInfoEnabled = function(e) {
            return b(e) ? (S = e, this) : S
        };
        var M = 10;
        this.onChangesTtl = function(e) {
                return arguments.length ? (M = e, this) : M
            }, this.$get = [“$injector”, “$interpolate”, “$exceptionHandler”, “$templateRequest”, “$parse”, “$controller”, “$rootScope”, “$sce”, “$animate”, “$$sanitizeUri”, function(t, n, r, o, s, l, g, D, A, O) {
                    function E() {
                        try {
                            if (!--Te) throw $e = void 0, zr(“infchng”, “{0} $onChanges() iterations reached. Aborting!\n”, M);
                            g.$apply(function() {
                                for (var e = [], t = 0, n = $e.length; t < n; ++t) try {
                                    $e[t]()
                                } catch (t) {
                                    e.push(t)
                                }
                                if ($e = void 0, e.length) throw e
                            })
                        } finally {
                            Te++
                        }
                    }

                    function I(e, t) {
                        if (t) {
                            var n, i, r, o = Object.keys(t);
                            for (n = 0, i = o.length; n < i; n++) r = o[n], this[r] = t[r]
                        } else this.$attr = {};
                        this.$$element = e
                    }

                    function L(e, t, n) {
                        we.innerHTML = “<span ” + t + “>”;
                        var i = we.firstChild.attributes,
                            r = i[0];
                        i.removeNamedItem(r.name), r.value = n, e.attributes.setNamedItem(r)
                    }

                    function q(e, t) {
                        try {
                            e.addClass(t)
                        } catch (e) {}
                    }

                    function V(t, n, i, r, o) {
                        t instanceof Ri || (t = Ri(t));
                        for (var a = /\S+/, s = 0, l = t.length; s < l; s++) {
                            var u = t[s];
                            u.nodeType === sr && u.nodeValue.match(a) && Se(u, t[s] = e.document.createElement(“span”))
                        }
                        var c = H(t, n, t, i, r, o);
                        V.$$addScopeClass(t);
                        var d = null;
                        return function(e, n, i) {
                            ue(e, “scope”), o && o.needsNewScope && (e = e.$parent.$new()), i = i || {};
                            var r = i.parentBoundTranscludeFn,
                                a = i.transcludeControllers,
                                s = i.futureParentElement;
                            r && r.$$boundTransclude && (r = r.$$boundTransclude), d || (d = U(s));
                            var l;
                            if (l = “html” !== d ? Ri(de(d, Ri(“<div>“).append(t).html())) : n ? Dr.clone.call(t) : t, a)
                                for (var u in a) l.data(“$” + u + “Controller”, a[u].instance);
                            return V.$$addScopeInfo(l, e), n && n(l, e), c && c(e, l, l, r), l
                        }
                    }

                    function U(e) {
                        var t = e && e[0];
                        return t && “foreignobject” !== F(t) && Hi.call(t).match(/SVG/) ? “svg” : “html”
                    }

                    function H(e, t, n, i, r, o) {
                        function a(e, n, i, r) {
                            var o, a, s, l, u, c, d, p, g;
                            if (f) {
                                var h = n.length;
                                for (g = new Array(h), u = 0; u < m.length; u += 3) d = m[u], g[d] = n[d]
                            } else g = n;
                            for (u = 0, c = m.length; u < c;) s = g[m[u++]], o = m[u++], a = m[u++], o ? (o.scope ? (l = e.$new(), V.$$addScopeInfo(Ri(s), l)) : l = e, p = o.transcludeOnThisElement ? G(e, o.transclude, r) : !o.templateOnThisElement && r ? r : !r && t ? G(e, t) : null, o(a, l, s, i, p)) : a && a(e, s.childNodes, void 0, r)
                        }
                        for (var s, l, u, c, d, p, f, m = [], g = 0; g < e.length; g++) s = new I, l = z(e[g], [], s, 0 === g ? i : void 0, r), u = l.length ? J(l, e[g], s, t, n, null, [], [], o) : null, u && u.scope && V.$$addScopeClass(s.$$element), d = u && u.terminal || !(c = e[g].childNodes) || !c.length ? null : H(c, u ? (u.transcludeOnThisElement || !u.templateOnThisElement) && u.transclude : t), (u || d) && (m.push(g, u, d), p = !0, f = f || u), o = null;
                        return p ? a : null
                    }

                    function G(e, t, n) {
                        function i(i, r, o, a, s) {
                            return i || (i = e.$new(!1, s), i.$$transcluded = !0), t(i, r, {
                                parentBoundTranscludeFn: n,
                                transcludeControllers: o,
                                futureParentElement: a
                            })
                        }
                        var r = i.$$slots = me();
                        for (var o in t.$$slots) t.$$slots[o] ? r[o] = G(e, t.$$slots[o], n) : r[o] = null;
                        return i
                    }

                    function z(e, t, n, i, r) {
                        var o, a, s = e.nodeType,
                            l = n.$attr;
                        switch (s) {
                            case or:
                                ne(t, ht(F(e)), “E”, i, r);
                                for (var u, c, d, p, f, m, g = e.attributes, h = 0, v = g && g.length; h < v; h++) {
                                    var b = !1,
                                        x = !1;
                                    u = g[h], c = u.name, f = Xi(u.value), p = ht(c), (m = _e.test(p)) && (c = c.replace(Yr, “”).substr(8).replace(/_(.)/g, function(e, t) {
                                        return t.toUpperCase()
                                    }));
                                    var T = p.match(Me);
                                    T && ie(T[1]) && (b = c, x = c.substr(0, c.length - 5) + “end”, c = c.substr(0, c.length - 6)), d = ht(c.toLowerCase()), l[d] = c, !m && n.hasOwnProperty(d) || (n[d] = f, Ge(e, d) && (n[d] = !0)), fe(e, t, f, d, m), ne(t, d, “A”, i, r, b, x)
                                }
                                if (a = e.className, $(a) && (a = a.animVal), w(a) && “” !== a)
                                    for (; o = y.exec(a);) d = ht(o[2]), ne(t, d, “C”, i, r) && (n[d] = Xi(o[3])), a = a.substr(o.index + o[0].length);
                                break;
                            case sr:
                                if (11 === Fi)
                                    for (; e.parentNode && e.nextSibling && e.nextSibling.nodeType === sr;) e.nodeValue = e.nodeValue + e.nextSibling.nodeValue, e.parentNode.removeChild(e.nextSibling);
                                ce(t, e.nodeValue);
                                break;
                            case lr:
                                W(e, t, n, i, r)
                        }
                        return t.sort(ae), t
                    }

                    function W(e, t, n, i, r) {
                        try {
                            var o = h.exec(e.nodeValue);
                            if (o) {
                                var a = ht(o[1]);
