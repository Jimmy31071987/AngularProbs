(function (app) {
    'use strict';
    app.directive('treeNode', function () {
        return {
            restrict: "E",
            scope: { nodes: '=', onClickNotify: "&onClick", },
            replace: true,
            transclude: false,
            template: function () {

                return '<ul>' +
                    '<li ng-click="onClick()">' +
                    '<a scroll-on-click ng-href="#{{nodes.Name}}">{{ nodes.Name }}</a>&nbsp;' +
                    '<span class="childcount" ng-show="nodes.Children" ng-bind="nodes.Children.length">&nbsp;</span>' +
                    '</li>' +
                    '<ul ng-if="nodes.Children" ng-show="nodes.Children">' +
                    '<div ng-repeat="child in nodes.Children">' +
                   
                    '<tree-node nodes="child"></tree-node>'+
                            '</div>' +
                        '</ul>' +
                      '</ul>'
            },
            link: function (scope, element, attrs) {
                return scope.onClick = function () {
                    if (element.find('li').eq(0).attr("class") == "toggle") {
                        element.find("li").eq(0).attr("class", "");
                    }
                    else {
                        if (scopes.node.Children != 'undefined' && scope.nodes.Children != null && scope.nodes.Children != "null" && scope.nodes.Children.length) {
                            element.find("li").eq(0).attr('class', 'toggle');
                        }
                    }
                    return true;
                }
            }
        }


    });

})(angular.module("common.ui"));
