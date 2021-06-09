![Screenshot 2021-06-09 at 10 29 55 AM](https://user-images.githubusercontent.com/52488112/121296178-d75ebc80-c90d-11eb-87f2-bd7af8916929.png)
# Animation  #Sparkle


import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        createLayer()
    }
    private func createLayer(){
        let layer = CAEmitterLayer()
        layer.emitterPosition = CGPoint(x: view.center.x, y: -100)
  
        let colors: [UIColor] = [
            .systemBlue,
            .systemRed,
            .systemPink,
            .systemGreen,
            .systemOrange,
            .systemYellow,
            .systemPurple
        ]
        let cells: [CAEmitterCell] = colors.compactMap {
            let cell = CAEmitterCell()
            cell.scale = 0.01
            cell.emissionRange = .pi * 2
            cell.lifetime=20
            cell.birthRate = 100
            cell.velocity = 200
            cell.color = $0.cgColor
            cell.contents = UIImage(named: "Image")!.cgImage
            return cell
        }
        
        layer.emitterCells = cells
        view.layer.addSublayer(layer)
    }

}

