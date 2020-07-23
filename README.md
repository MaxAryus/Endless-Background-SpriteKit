# EndlessBackgroundSpriteKit

//
//  ground generation.swift
//  Jump
//
//  Created by Max Aryus on 23.07.20.
//  Copyright © 2020 Max Aryus. All rights reserved.
//

import SpriteKit

extension GameScene {
    
    func setupBackground() {
        
        let background = SKSpriteNode(imageNamed: "background")
        background.name = "Background"
        background.size = CGSize(width: self.frame.size.width + 30, height: self.frame.size.height)
        background.position = CGPoint(x: 0 * self.frame.size.width / 2, y: (self.frame.size.height) - self.frame.size.height)
        self.addChild(background)
        
        let background1 = SKSpriteNode(imageNamed: "background")
        background1.name = "Background"
        background1.size = CGSize(width: self.frame.size.width + 30, height: self.frame.size.height)
        background1.position = CGPoint(x: 2 * self.frame.size.width / 2, y: (self.frame.size.height) - self.frame.size.height)
        self.addChild(background1)
    }
    func moveGround() {
        self.enumerateChildNodes(withName: "Background") { (node, error) in
            node.position.x -= self.scrollSpeed * CGFloat(self.fixedDelta)
            
            if node.position.x < -self.frame.size.width {
                node.position.x += self.frame.size.width * 2
            }
        }
    }
    
    
}

